Palo Alto guide: How to Implement and Test SSL Decryption
https://knowledgebase.paloaltonetworks.com/KCSArticleDetail?id=kA10g000000ClEZCA0&lang=en_US
How to generate a new self-signed SSL Certificate
https://knowledgebase.paloaltonetworks.com/KCSArticleDetail?id=kA10g000000Cla8CAC

Establish device certificates
If your network has a certificate authority, use this external CA, otherwise (as in CCDC) you may generate these locally.

Navigate to **Device > Certificates** and click **Generate**. First create your Forward Trust certificate
with an appropriate name, a unique common name, checkmark *Certificate Authority* and apply certificate attributes to prevent device confusion.

Do the same for your Forward Untrust certificate authority.

Click on each CA once generated and checkmark the appropriate characteristic
![[Pasted image 20250213113125.png]]


## Install certificates on devices
### Linux
Download certificate as *Base64 Encoded Certificate (PEM)* to device.

Copy the .crt file to the certificate store
`cp *.crt /usr/share/ca-certificates/`

Extract the certificates 
`sudo dpkg-reconfigure ca-certificates`

Validate the installed certificates
`ls /etc/ssl/certs | grep "[CERT NAME]`

## Windows
Double click on .crt file. Installer will open. Install to trusted root CA directory.

