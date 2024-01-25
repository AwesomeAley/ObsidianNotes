The 8 core design principles when designing secure IT infrastructure

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

**Least Privileges**
Each process and user should have the minimum set of privileges needed to preform their tasks
- *violation*: Users accumulate privileges over time, which are never revoked

**Least Common Mechanism**
Use different mechanisms for different users or groups to gain access to a resource; shared mechanisms are a pathway for attacks
- *violation*: The same webpage is used for signing in normal users and site administrators

**Psychological Acceptability**
The security mechanism should not be so annoying it makes the users turn it off or circumvent usage of the measure.
- *violation*: The security mechanism locks the screen for some time/contrived over-complex multi-authentication

