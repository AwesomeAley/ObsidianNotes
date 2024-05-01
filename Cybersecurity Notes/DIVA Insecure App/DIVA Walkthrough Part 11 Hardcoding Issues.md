# 12 Hardcoding Issues - Part 2
![[Pasted image 20240501184841.png]]

We look at "Hardcode2activity.class" in the decompiler and note that the secret is stored in an object of the type "DivaJni". This is a native code file so we look at "DivaJni.class" to see the name of the library that is loaded.
![[Pasted image 20240501185032.png]]

In the extracted files we look for the library name ![[Pasted image 20240501185120.png]]

To open the binary and read the ASCII, we can use the **strings** command in the terminal.