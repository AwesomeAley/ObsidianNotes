Security profiles to be added to policies for added monitoring/protection
Navigate to **Objects > Security Profiles**
## Antivirus
The antivirus profile scans for malware
Click *Add* to create a new profile. Name it.

In the *Action* tab:
For north-south bound traffic set actions to drop. 
For east-west bound traffic set actions to reset-both
![[Pasted image 20250213094155.png]]

In the *Wildfire Inline ML* tab:
enable inline machine learning to stop 0 day attacks
![[Pasted image 20250213094135.png]]

## Anti Spyware
Click *Add* to create a new profile. Name it.

In the *Signature Policies* tab:
for north-south bound traffic set actions to drop for critical and high and set alert for all other severity levels
for east-west set actions to rest-both for critical and high and set alert for other severity levels. 

In the *DNS Policies* tab:
Set the DNS security policy to sinkhole (you may consider setting up your own sinkhole server to capture intelligence on Red Team or use the loopback address as the sinkhole)
![[Pasted image 20250213094553.png]]

## Vulnerability Protection
Click *Add* to create a new profile. Name it.

For north-south bound traffic set actions to drop for critical and high and set actions to alert for all other severity levels.
For east-west traffic set actions to reset-both for critical and high and set alert for other severity levels
![[Pasted image 20250213094811.png]]

## URL Filtering
Click *Add* to create a new profile. Name it.

In the *Categories* tab:
At a minimum block these categories of URLs
- command and control
- grayware
- hacking
- malware
- newly registered domains
- proxy avoidance and anonymizers
- ransomware
Set all other categories to alert

In the *Inline ML* tab:
stop 0 day attacks by enabling inline machine learning action to block for all
![[Pasted image 20250213095125.png]]

## File Blocking
Click *Add* to create a new profile. Name it.

Block downloading and uploading dangerous files.
Alert on all file uploads and downloads
![[Pasted image 20250213095224.png]]



