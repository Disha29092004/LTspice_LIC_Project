# EXPERIMENT 1
## DC, Transient and AC analysis of Common Source Amplifier Using LTspice
### Components : 
n-mosfet (180nm technology node), Resistor-1K ohm, Voltage source(V) (1.8V,0.9V), AC ground, Wries.

### Circuit Diagram 1 : 
\
![Image](https://github.com/user-attachments/assets/10fcd548-9b0b-4178-88a1-8ae4740b3d00)

### Theory :
The common source amplifier is one of the most widely used configurations in analog electronics due to its high voltage gain, making it ideal for signal amplification applications. The behavior of this amplifier is analyzed in three key domains:\
DC analysis: Determines the biasing conditions and operating point.\
Transient analysis: Evaluates the time-domain response.\
AC analysis: Examines small-signal behavior and frequency response.\
<br>
DC analysis: In DC analysis the goal is to establish the stable operationg point for the MOSFET, ensuring it remains in the saturation region for proper amplification.The MOSFET operates in the saturation region when drain-source voltage(V<sub>DS</sub>) is greater than the overdrive voltage (V<sub>OV</sub>=V<sub>GS</sub>-V<sub>TH</sub>). the drain current is given by\
 <br>       I<sub>D</sub>= 1/2K<sub>n</sub>(V<sub>OV</sub>)<sup>2</sup> \
<br>V<sub>DS</sub> and I<sub>D</sub> provides the operating point of the MOSFET.\
<br>Transient analysis: Transient analysis examines how the amplifier responds to time-varying signals, such as pulse inputs or sudden changes in voltage. The behavior depends on the charging and discharging of capacitors, including coupling and bypass capacitors. The amplifier's response to sudden input changes is limited by its time constants, which are determined by the capacitance and resistance in the circuit. Transient analysis is crucial in high-speed applications where parameters like rise time, fall time, and propagation delay determine the amplifier's suitability for fast signal processing.\
<br>AC analysis: In AC analysis MOSFET treated as a linear small-signal amplifier, where the drain current is proportional to small variations in gate volatge\
<br>i<sub>D</sub>=g<sub>m</sub>v<sub>gs</sub>\
<br>where g<sub>m</sub> is transconductance.The volatge gain of the amplifier is give by \
<br>A<sub>v</sub>= -g<sub>m</sub>(R<sub>D</sub>||R<sub>L</sub>\)
<br>The negative sign indicates the 180 degree phase shift between the input and output signals. The input impedance is primarily calculated by the gate biasing resitors whereas output impedance is largely influenced by the resistor R<sub>D</sub> . At low frequency the gain is effected by coupling capacitors and bypass capacitors, while at high frequencies by paracitic capacitors.\

### Procedure :
Common Source Amplifier Circuit Design Using LTspice
1. Construct the common source amplifier circuit as per the circuit diagram in LTspice.
2. Set resistor value to 1KΩ, DC supply voltage to 1.8V, and gate voltage to 0.9V.
3. Download the library file tsmc018 (1).txt.
4. Create a folder and save both the library file and LTspice project files in it.
5. Import the library file into LTspice using a SPICE directive (.op).
6. Set the MOSFET model name to CMOSN as specified in the library file, with a channel length of 180nm and width of 1μm.
7. Calculate the required current value for the given power rating.
8. DC Analysis: In the simulation settings, choose DC sweep, adjust the DC offset, and obtain a list of output values. Vary 
   the MOSFET width to observe changes in drain current (Id) while keeping other parameters constant.
9. Transient Analysis: In the simulation settings, select transient analysis. Set DC offset to 0.9V, amplitude to 50mV, 
   frequency to 1kHz, and stop time to 3ms to obtain the transient response waveform.

10. AC Analysis: In the simulation settings, choose AC analysis with a decade sweep, 20 points per decade, and frequency 
    range from 0.1Hz to 1THz to generate the AC response waveform.


### Calculatiom: 
Take power as 100uW\
We know that P=VI , where V=1.8V here \
Therefore, I = 55.5uA\
From loop equation : V<sub>DD</sub> = I<sub>D</sub>R<sub>D</sub> + V<sub>out</sub> \
where V<sub>DD</sub>= 1.8, I<sub>D</sub>=55.5uA, R<sub>D</sub>=1KHz\
Therefore V<sub>out</sub>= 1.745V\
Hence Q point= (1.745V, 55.5uA)
### Tabular Column:
| Width | CurrentI<sub>D</sub> | V<sub>out</sub>  |
|-------|----------------------|------------------|
|  1um  |        152.7uA       |      1.64V       |
| 0.8um |        127.8uA       |      1.67V       |
| 0.4um |        78.37uA       |      1.721V      |
| 0.3um |        66.39uA       |      1.733V      |
| 0.2um |        55.2uA        |      1.744V      |
|0.201um|        55.3uA        |      1.744V      |
|0.203um|        55.5uA        |      1.745V      |
### Result:
1. DC analysis:
   ![Image](https://github.com/user-attachments/assets/2e5ca3cb-b2a1-490a-89df-37e9c614dba4)

   we got I<sub>D</sub>= 55.5uA\
          width = 0.203um\
   Vout= 1.745V\
   we get DC operating point as (1.745V, 55.5uA)
3. Transient analysis:
   ![Image](https://github.com/user-attachments/assets/f5a2507b-378b-4717-b850-3a16025447a4)

   we got V<sub>out</sub>= 1.745V for width of 0.203um\
   And a phase shift of 180 degree.
5. AC analysis:
   ![Image](https://github.com/user-attachments/assets/c864c284-7340-4d79-b87c-cdabfe5a9c49)

    we got frequency = 210.45GHz\
          Gain(dB) = -9.104dB\
### Inference: 
1. The MOSFET drain current (Id) is directly proportional to its width, with other parameters held constant.
2. DC analysis provides the DC operating point and verifies that the MOSFET operates in the saturation region.
3. Transient analysis illustrates the MOSFET's response to time-varying AC signals (such as a sine wave).
4. The output signal is amplified with a 180-degree phase shift relative to the input.
5. AC analysis provides the amplifier’s voltage gain and frequency response.
   <br>


### Circuit Diagram 2:
![Image](https://github.com/user-attachments/assets/34782522-ccf9-47a9-a6dd-cfde838df83e)

### Components: 
PMOSFET,NMOSFET (180nm), voltage supply(1.8,0.7), AC ground, wires.

### Theory :

The common source amplifier is one of the most widely used configurations in analog electronics due to its high voltage gain, making it ideal for signal amplification applications. The behavior of this amplifier is analyzed in three key domains:\
DC analysis: Determines the biasing conditions and operating point.\
Transient analysis: Evaluates the time-domain response.\
AC analysis: Examines small-signal behavior and frequency response.\
<br>
DC analysis: In DC analysis the goal is to establish the stable operationg point for the MOSFET, ensuring it remains in the saturation region for proper amplification.The MOSFET operates in the saturation region when drain-source voltage(V<sub>DS</sub>) is greater than the overdrive voltage (V<sub>OV</sub>=V<sub>GS</sub>-V<sub>TH</sub>). the drain current is given by\
 <br>       I<sub>D</sub>= 1/2K<sub>n</sub>(V<sub>OV</sub>)<sup>2</sup> \
<br>V<sub>DS</sub> and I<sub>D</sub> provides the operating point of the MOSFET.\
<br>Transient analysis: Transient analysis examines how the amplifier responds to time-varying signals, such as pulse inputs or sudden changes in voltage. The behavior depends on the charging and discharging of capacitors, including coupling and bypass capacitors. The amplifier's response to sudden input changes is limited by its time constants, which are determined by the capacitance and resistance in the circuit. Transient analysis is crucial in high-speed applications where parameters like rise time, fall time, and propagation delay determine the amplifier's suitability for fast signal processing.\
<br>AC analysis: In AC analysis MOSFET treated as a linear small-signal amplifier, where the drain current is proportional to small variations in gate volatge\
<br>i<sub>D</sub>=g<sub>m</sub>v<sub>gs</sub>\
<br>where g<sub>m</sub> is transconductance.The volatge gain of the amplifier is give by \
<br>A<sub>v</sub>= -g<sub>m</sub>(R<sub>D</sub>||R<sub>L</sub>\)
<br>The negative sign indicates the 180 degree phase shift between the input and output signals. The input impedance is primarily calculated by the gate biasing resitors whereas output impedance is largely influenced by the resistor R<sub>D</sub> . At low frequency the gain is effected by coupling capacitors and bypass capacitors, while at high frequencies by paracitic capacitors.\


<br>
### Procedure :
1. Construct the common source amplifier circuit in LTspice according to the provided circuit diagram. \
2. Set the resistor value to 1kΩ, the DC supply voltage to 1.8V, and the gate voltage to 0.9V. \
3. Download the library file tsmc018 (1).txt. \
4. Create a new folder and save both the library file and the LTspice project file in it. \
5. Import the library file into LTspice using a SPICE directive (.op). \
6. Use the MOSFET model name CMOSN from the library file, with a channel length of 180nm and a channel width of 1µm. \
7. Calculate the current value for the specified power rating. \
8. For DC analysis, go to the simulation settings, select DC sweep, and adjust the offset to obtain a range of current 
   values from the circuit. Modify the transistor's width to observe changes in drain current (Id), keeping other  
   parameters constant, as the drain current is directly proportional to the width.\
9. For transient analysis, modify the simulation settings from DC sweep to transient. Set the DC offset to 0.9V, amplitude 
   to 50mV, and frequency to 1kHz. Set the stop time to 3ms and run the simulation to observe the expected waveform. \
10.For AC analysis, change the simulation settings from transient to AC analysis. Choose a decade sweep type, set 20 points 
   per decade, and specify the frequency range from 0.1Hz to 1THz to obtain the desired AC response waveform. \
### Calculatiom: 
Take power as 100uW\
We know that P=VI , where V=1.8V here \
Therefore, I = 55.5uA\
We get Vout= 1.704 which is V<sub>DS</sub>\
we get Q point = (V<sub>DS</sub>, I<sub>D</sub>)= (1.704V, 55.5uA)\

### Tabular Column:
| Width | CurrentI<sub>D</sub> | V<sub>out</sub>  |
|-------|----------------------|------------------|
|  1um  |        50.9uA        |      1.704V      |
|1.01um |        51.4uA        |      1.704V      |
|1.04um |        52.9uA        |      1.704V      |
|1.06um |        53.9uA        |      1.704V      |
|1.09um |        55.3uA        |      1.704V      |
|1.092um|        55.4uA        |      1.704V      |
|1.093um|        55.5uA        |      1.704V      |
<br>

### Simulation Result:
1. DC analysis :
   ![Image](https://github.com/user-attachments/assets/5e143440-2592-4977-a32f-65df705e79ad)
    we got I<sub>D</sub>= 55.5uA\
          width = 1.093um\
   Vout= 1.704V\
   we get DC operating point as (1.704V, 55.5uA)
  
2. Transient analysis:
   ![Image](https://github.com/user-attachments/assets/42a6d74e-5929-43ee-b509-860aeef264ed)
    we got V<sub>out</sub>= 1.704V for width of 1.093um\
   And a phase shift of 180 degree.
  
3. AC analysis:
   ![Image](https://github.com/user-attachments/assets/5a442856-bc1a-40ce-924e-62b7c430a3ac)
we got frequency = 75.739GHz\
          Gain(dB) = 70.149mdB

### Inference: 
1. A diode-connected MOSFET always operates in the saturation region. 
2. The drain current is directly proportional to the transistor's width, assuming other parameters remain constant. 
3. DC analysis helps determine the DC operating point and confirms whether the MOSFET is in the saturation region. 
4. Transient analysis demonstrates how the MOSFET responds to a time-varying AC signal (such as a sine wave). 
5. The output is amplified with a 180-degree phase shift relative to the input. 
6. AC analysis provides the gain and frequency response of the MOSFET. 
   <br>
