#### Authentication Profiles
First create an authentication profile to define how users authenticate when accessing the firewall
Navigate to **Device > Authentication Profile**

Server profiles (**Device > Server Profiles**) can be created for relevant authentication methods such as LDAP or Kerberos to be implemented into authentication profiles
Example (RADIUS):
![[Pasted image 20250211101225.png]]
Authentication sequences (**Device > Authentication Sequence**) can be used if multiple authentication profiles are to be checked for each user. Position defines sequence.
Example (LDAP and RADIUS):
![[Pasted image 20250211101058.png]]
#### Adding Users
(If using Local-Database as authentication method) Users can then be added to the Local User Database
Navigate to **Device > Local User Database > Users**

Administrators can be added to **Device > Administrators**
Here authentication profiles created as detailed above will be used to determine how users authenticate
