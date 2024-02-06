How do we encode bits in a radio wave (Digital to Analog)

The basic idea is to alter, or modulate, one or more of the parameters of the wave to indicate a 0 or 1.

**AM (Amplitude Modulation)** - Increase or decrease the wave's amplitude

**FM (Frequency Modulation)** - Modify the wave's frequency

**Phase Modulation** - Shift the wave's phase by a positive or negative amount.

Newer WI_FI standards use a combination of both phase and amplitude modulation to encode a larger number of bits: Quadrature Amplitude Modulation (64QAM, 256 QAM)
64 QAM:
![[Pasted image 20240206120331.png]]

## Error Correction
The more bites you pack into a waveform, with smaller differences in modulation, the more errors that occur due to noise

New types of modulation such as QAM256 that encode larger numbers of bits in the signal are only practical in combination with sophisticated error correcting algorithms 
A simple type of error correcting code is a checksum added to the end of a chunk of data.