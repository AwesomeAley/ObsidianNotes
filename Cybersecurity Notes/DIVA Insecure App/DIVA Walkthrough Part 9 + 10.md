## 9 Access Control Issues - Part 1
![[Pasted image 20240501181023.png]]
We first run locat on our debugger bridge to watch activity as we launch the app on the phone.
![[Pasted image 20240501180847.png]]

We see the activity being run
![[Pasted image 20240501180906.png]]

We then run 
**./adb shell am start -n jakhar.aseem.diva/.APICredsActivity**
to see that the activity can be started by any application including us on the ADB.

