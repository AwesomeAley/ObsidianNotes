**Economy of Mechanism**
Use the smallest, simplest set of hardware/software that does what you want; the fewer moving pieces a system has, the less there is so exploit.
- *violation*: "Feature creep" unnecessary addition of features

**Fail-Safe defaults**
The default setting should be the one that keeps things locked down. Then they can be opened up if needed.
- *violation*: The config file that ships with a database package gives everyone access by default or default passwords set

**Complete Mediation**
Every action should be checked against the access control mechanism
- *violation*: permissions are never checked again after verification

**Open Design**
The design of a security mechanism should not be the secret part
- *violation*: utilizing obscure security systems that you don't understand

**Separation of Privileges**
Use different privilege attributes for different actions
- *violation*: A single "administrator" account with permissions for everything

