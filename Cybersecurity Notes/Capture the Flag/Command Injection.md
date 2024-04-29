**Incredible Info:** https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Command%20Injection

### FlyerCTF Pinger_1
"Pinger" website utilizes no input cleansing, solely appends user input to `ping -c 4` and executes it on the host. Appending multiple commands within one input with `;`, you can run multiple commands. 
![[Pasted image 20240427120952.png]]

running `; cd ..; ls -a` reveals "flag.txt" which can then be opened similarly. `;cd ..; cat flag.txt`

![[Pasted image 20240427121024.png]]

### FlyerCTF Pinger_2
This time there are input filters put into place. Semicolons, and the "cat" command are now blocked. To bypass this, we use `&&` (run the second command after the first succeeds), and we input "cat" as `c\at`, which bypasses the filters. These methods are described in **PayloadsAllTheThings/CommandInjection***.

![[Pasted image 20240427130859.png]]