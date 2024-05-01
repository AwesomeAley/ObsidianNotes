# 9 Access Control Issues - Part 1
![[Pasted image 20240501181023.png]]
We first run locat on our debugger bridge to watch activity as we launch the app on the phone.
![[Pasted image 20240501180847.png]]

We see the activity being run
![[Pasted image 20240501180906.png]]

Then, from the root adb shell, use the am start command, using the -n option to start the found activity by its name, and the -a option to trigger the action by its name. This simulates pressing the button, and you should see the app screen change to show the credentials. This illustrates that any app can obtain the credentials by triggering the activity.

We then run 
**./adb shell am start -n jakhar.aseem.diva/.APICredsActivity**
to see that the activity can be started by any application including us on the ADB.

# 10 Access Control Issues - Part 2
![[Pasted image 20240501182407.png]]
The information is only shown if a PIN has already been entered. We run logcat as earlier to find the application.
![[Pasted image 20240501182449.png]]

We now use **Java Decompiler** to view the extracted `classes-dex2jar.jar` file and view the associated file. We see that there is a conditional that makes sure that a certain value is not True and then shows the information:
![[Pasted image 20240501182614.png]]
We search up the variable name of the string in "R.class" also in the Java Compiler:
![[Pasted image 20240501182756.png]]

In the decompiled application folder there is a subfolder **res/values/** with "strings/xml" where was get the value of the variable.
![[Pasted image 20240501182821.png]]

We can then write the command with the variable set accordingly to get the application to run and show us the information we are looking for:
`**adb shell am start -n jakhar.aseem.diva/.APICreds2Activity -a jakhar.aseem.diva.action.View_CREDS2 --ez check_pin false**`
![[Pasted image 20240501182935.png]]


