Digital computers were invented, and by the late 1950s, there was a demand to network the growing number of business computers being deployed by large companies.

Methods were invented for transmitting digital data between computers over the standard PSTN, using acoustic couplers and telephone sets, creating the first modems. (modulator/demodulator)
	- the noisy nature of the analog-to-digital conversion performed by modems limited the speeds of digital communications.
	- speeds began at 300 bps (baud) and maxed out at ~56kbps in the early 1990s

Before the advent of powerful personal computers, modems also enabled "dumb terminals" to log in remotely to the mainframe. 

#### From Analog to Digital Networks: Circuit Switching vs. Packet Switching
Telephone and teletype networks used **circuit switching**, in which a closed-loop electrical circuit is created between the endpoint of each connection. 
- inefficient, because each connection requires an exclusive circuit
- if the circuit is broken at any point, the whole connection fails.
The development of **packet switching** enabled the next leap in long-distance digital communication.
- messages are digitized and chopped up into a series of packets; each packet has a header with information about which connection it is a part of.
- The same physical wires can be used for many logical connections; routers and switches examine packets to route them to their destination
Much more robust, because losing individual packets doesn't terminate the connection and packets can use multiple routes to get to their destination routing around congestion and failures. This method was also implemented for telephone communication.

#### The Internet
The U.S. government's Advanced Research Projects Agency (ARPA) became involved in research and development of computer networks.

The ARPANET (est. 1969) was the precursor to the internet, the first public packet-switched data network; further packet switching research led to the development of the TCP/IP protocols

Multiple factors contributed to the explosion of participation in the internet starting around 1994:
- personal computers becoming powerful enough to multi-task and present multimedia content
- the emergence of the world-wide web from http and html, and browsers as a user-friendly interface to online data.

#### The Birth of Wireless
The discovery of electromagnetic waves (James Clerk Maxwell) experimentally verified by Heinrich Hertz) led to the idea that they could be used to transmit information invisibly through the air

Italian inventory Guglielmo Marconi successfully sent the first radio transmission (a morse code message) in 1895.

Soon modulation techniques were developed to encode sound directly in the signal, and powerful transmitters enabled radio broadcasting into people's homes.

In the 80s, computing became personal, in the 90s and 00s, with the rise of the laptop form factor: it became mobile
- early laptops were considered devices for working "offline"
- however the rise of the internet soon created demand for connectivity everywhere

The use of two way radios to encode and transmit data over short distances was already understood; what was needed was protocols to establish wireless LANs, taking advantage of an upstream wired internet connection
The IEEE led a standardization process for protocols designed to interoperate with the Ethernet 802 series of standards

#### The Mobile Telephony and Data Revolutions
IN the early 1980s, the first analog mobile phone system, called Advanced Mobile Phone System (AMPS), became commercially available, soon replaced by the CDMA standard in the US and GSM in Europe.

The system is also essentially based on short-range two-way radio communication, but designed from the beginning for roaming between multiple base stations. (towers)

The growth of cellular telephones drove advances in radio data transmission technology.
The first attempts to provide data communication over cellular network were slow and unreliable. But with the advent of 3G, it became practical to connect to the internet over the cellular network.
