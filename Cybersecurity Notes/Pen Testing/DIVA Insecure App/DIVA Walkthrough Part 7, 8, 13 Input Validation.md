
# 7 Input Validation Issues - Part 1
This challenge involves SQL injection, as the user input is not sanitized in anyway. Entering `'OR '1' == '1` outputs all the user info for all users.

![[Screenshot 2024-05-01 174441.png]]

# 8 Input Validation Issues - Part 2
![[Pasted image 20240501175800.png]]
We remember from earlier challenges that there is an XML file storing user passwords in **data/data/jakhar.aseem.diva/shared_prefs/**. So we enter it in place of an URL with `file:///data/data/jakhar.aseem.diva/shared_prefs/jakhar.aseem.diva_preferences.xml`
![[Pasted image 20240501175912.png]]


# 13 Input Validation Issues - Part 3
![[Pasted image 20240501185615.png]]

Buffer Overflow! Input a shit ton of random characters to crash the app! 
![[Pasted image 20240501185826.png]]