First create a server script utilizing the Python sockets library

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