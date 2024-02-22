#### Security Goals of WIFI Cryptography
**User Authentication**: 
- Ensuring that only authorized users may associate and exchange data
- may be per user or with one pre-shared key for the whole network
- achieved by a challenge-response protocol in which the client proves it knows a key or passphrase
**Data Privacy**:
- ensuring that the contents of the eavesdropped packets cannot be determined
- Achieved by symmetric encryption algorithms, data is not sent as *cleartext*
**Data Integrity**
- Ensuring that wireless frames cannot be modified or forged without detection
- achieved by message integrity protocols

### Wired Equivalent Protocol (WEP)
Authentication and encryption method introduced with the original 802.11 standard. This is not intended to be perfectly secure, but as secure as the wired ethernet equivalent.  Significant weaknesses found early on.

