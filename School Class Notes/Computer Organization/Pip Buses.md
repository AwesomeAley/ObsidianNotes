Pip-1 address/data bus can only transfer 1 "byte" at a time.
Traffic Jams -bus contention- Use the TRI-STATE logic to prevent bus contention:
TRI-STATE gate: 3 states with **enable input**
- 0 = disable
- 1 = enable
- (opposite of the way the real world works)
Adding an enable input to a gate produces 3rd logic gate
- enable at 0, gate electronically disconnected from output
- 3rd state: floating (high-impedance state)

### BUFFER (Truth) Gate

![[Pasted image 20231030102021.png]]

### Tri-State Gate

![[Pasted image 20231030102059.png]]
