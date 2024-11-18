The server that runs the AD services is called the **Domain Controller (DC)**

To configure users, groups or machines in Active Directory, we need to log in to the Domain Controller and run "Active Directory Users and Computers" from the start menu
![[Pasted image 20241104214048.png]]


Right click any organizational unit or object(users, etc.) for options such as editing their passwords.

For advanced features click on 'View' and then 'Advanced Features':
![[Pasted image 20241104214237.png]]

Disable deletion protection through properties of OU or object
![[Pasted image 20241104214318.png]]

#### Delegation of Control:
You can give users control over OUs by right clicking them and clicking on 'Delegate Control'


#### Group Policy Management
Use the Group Policy Management tool
![[Pasted image 20241104214854.png]]

Create a GPO under 'Group Policy Objects' then link it to the OU

![[Pasted image 20241104215114.png]]

Create new GPOs within 'Group Policy Objects'![[Pasted image 20241104220351.png]]
Right click and 'edit' to set policies. (There are loads. Such as setting password length limits)

Then drag them to OUs to apply to them