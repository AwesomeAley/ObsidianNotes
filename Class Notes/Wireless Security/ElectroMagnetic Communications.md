All wireless communications are by means of electromagnetic (EM) waves. All radiation on the spectrum are the same type of EM waves, just at different frequencies. They propagate at the speed of light: c~ 300,000,000 m/s (5.879 trillion miles)

A fundamental property of an EM wave is its **frequency**, measured in Hertz, which is cycles per second.
- 1 hz = 1 cycle/second
**Wavelength** is the distance between successive peaks of a wave. Because it is distance, it is measured in the SI unit of meters. It is inversely proportional to frequency (higher frequency means shorter wavelength) We can easily find the wavelength of any frequency wave with the following formula:

wavelength  = propagation speed / frequency

**Amplitude** is the maximum displacement of a wave. We think of it as simply the signal's strength or power. Measured in watts
For 2.4GHz, WI-FI "full power" of a transmitting AP is 100mW. For 5GHz, its 200mW.
Typically client devices will use lower power to save battery life. A smartphone will typically transmit with 15mw.
Consumer microwave ovens use RF emissions at a frequency of 2.45 Ghz but a typical power of 1000 watts
AM radio towers may transmit with power of up to 50,000 watts

**Phase** is a measure of how much the peaks of two waves at the same frequency are in or out of alignment. Measured in degrees between 0 (fully in phase) and 180 (fully out of phase).

#### Propagation and Attenuation
How RF waves *propagate*, or spread out from their point of transmission, is crucial to the quality of signal received and how quickly and reliably data can be transmitted.

Weakening or loss of a signal is called *Attenuation*

Attenuation happens naturally over increased distance, as the wave spreads out and less of its strength can be picked up at any one point.
Attenuation is also affected by the physical environment; physical materials absorb and deflect wave's energy. Denser materials cause more attenuation, and conductive materials case more interference than non-conductive.

#### Phenomena that Affects Propagation
**Absorption** 
- A material may absorb a portion of a signal
- Drywall will weaken a 2.4GHz Wi-Fi signal to half of its original power
- A brick wall will weaken it 1/16 of its original power
**Reflection**
- A wave may bounce off an object in a different direction
- metal objects obviously reflect; glass and concrete can as well
- Reflection is a major cause of Wi-Fi performance degradation; reflected waves can interfere with each other, causing attenuation or corruption.
**Scattering**
- Scattering is best described as multiple reflections in multiple directions
**Refraction**
Passing through mediums of different density can cause RF signals to be bent so that its travel continues at a different angle

### Measuring Attenuation in dB
The power of Wi-Fi signals at the reception point is measured as loss or attenuation from the transmitted signal: a *relative* not absolute measure

Measured in *decibels* (dB), which are a base-10 logarithmic scale
- specially for receivers, measured in dBm, or decibel-milliwatts, for EM applications
  - Remember, logarithm of a fraction is a negative number: all signal strength values will  be negative
  - Every -10 dB represents a reduction of the absolute power in mW by 1/10
  Example: A signal of -30 dBm is what fraction of the original power: 1/1000

### Antennas 
Antennas are essential for both sending and receiving wireless signals. AN antenna acts as a receiver when the electromagnetic waves of the RF signal induce an electrical current in the antenna which is then measured. Any piece of metal can be used as an antenna. An omnidirectional Wi-Fi antenna radiates 360 degrees on the horizontal plane and between 7 and 80 degrees on the vertical plane (assuming the antenna is positioned vertically). You should have multiple angles.
**Gain** is the measure of how much an antenna concentrates or directs a signal.