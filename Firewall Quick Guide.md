Turn off the management interface and data external interface temporarily - you don't know who's accessing it
CLI:
```
configure
set deviceconfig system permitted-ip 127.0.0.1
set network interface ethernet ethernet1/1 link-state down
commit
```
