https://www.youtube.com/watch?v=f0hHcITXqDw

Getting connected

Firewall gui can be accessed on ip of firewall

![[Pasted image 20240215113030.png]]

Basic initial firewall appliance security should be established [[Initial Securing of Firewall]]

In the `Device` menu 
### Retrieve Licenses
device > licenses
![[Pasted image 20240215125740.png]]

### Dynamic Updates
device > dynamic updates > antivirus
device > dynamic updates > applications and threats
Download and Install new updates 
![[Pasted image 20240215125940.png]]
a schedule for routine updates can be set

### Update Software
![[Pasted image 20240215130416.png]]
reboot post installation


### Add basic default firewall policy
add basic firewall policy with default security profiles to secure outbound connections to some degree before more specific policies are made
![[Pasted image 20240215134655.png]]

set source as trusted and destination as untrusted (external)
![[Pasted image 20240215134950.png]]

set profile settings to default
![[Pasted image 20240215135038.png]]