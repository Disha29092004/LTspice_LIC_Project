# DIFFERENTIAL PAIR AMPLIFIER : <br>
<br>
1. A differential pair amplifier, also called a long-tailed pair.<br>
2. Differential pair amplifier is a fundamental circuit in analog electronics, especially in operational amplifiers and differential signal processing.<br>
3. It consists of two transistors that share a common current source and amplify the difference between two input signals.<br>
<br>

## BASIC STRUCTURE : <br>
![Image](https://github.com/user-attachments/assets/1e25c387-15ff-417e-bf8e-a23af72440ad)
1. Two NMOS transistors with their sources tied together.<br>
2. A current source at the sources.<br>
3. Outputs taken from the drains.<br>
<br>

### WORKING PRINCIPLE : <br>
1. It receives two input signals (Vin1 and Vin2).<br>
2. The circuit amplifies the difference between these signals, rejecting common-mode noise.<br>
3. A constant current source in the emitter ensures proper operation.<br>
<br>

#### DESIGN QUESTION :
![Image](https://github.com/user-attachments/assets/90a87d42-759f-4c83-b5a9-989b8884632b).<br>

## CIRCUIT 1 : Resistor-Loaded Differential Pair:<br>

### DC Analysis :<br>
1. The DC operating points are determined.
* Objective: Ensure both transistors are in saturation.
* Vary W/L to get the required Voutcm. <br>
* Vary Rd to set exact Voutcm.<br>
* Results:<br>
  Drain current (Id) is split between the two MOSFETs.<br>
  Drain-to-source voltage (Vds) is checked to ensure saturation.<br>
![Image](https://github.com/user-attachments/assets/25cbc8db-e5a5-4e01-8f26-9de17cc6f9a2).<br>

##### Theoretical values and observed values of parameters :<br>

| Parameter    | Theoretical value  | Practical value |
|--------------|--------------------|-----------------|
|Voutcm        | 1.25V              | 1.250V          |
|Vp            | 0.4V               | 0.4V           |
|Id1,Id2       | 0.5mA              | 4.9mA          |
|Id(V1)        | 1mA                | 0.99mA          |
|Rd            | 1.9kohm            | 1.9kohm        |
|Rss           | 400.0ohm           | 400ohm          |
|Vgs           | 0.8V               | 0.801V          |

<br>

Now lets caluculate vincm(min), Vincm(max), Vout(min), Vout(max) .<br>
![Image](https://github.com/user-attachments/assets/172fba57-73ae-4237-aa37-0aace33617d1).
<br>

### Transient Analysis :
1. A time-varying differential input signal is applied.
* Objective: Observe real-time voltage amplification.
* Results:
  The output waveform shows amplification of the differential signal.
  Common-mode signals are effectively suppressed.
  The circuit response is linear for small input variations.
* Replace DC input with an AC signal.<br>
* Use SINE(dc_offset, Amplitude, Frequency),
* Go to "Simulate" > "Edit Simulation Cmd" > "Transient".<br>
* Set Stop Time: 5ms.<br>
* Run the simulation.<br>
##### I will apply.<br>
### * Amplitude = 50mV :
#### * When Vincm = 1.2V:
![Image](https://github.com/user-attachments/assets/0b74b51b-1bed-46ef-8545-a70ab11a647d)
<br>

### AC Analysis : <br>
A small-signal AC analysis is performed.
Objective: Measure voltage gain, bandwidth, and CMRR.
Results:
Differential gain (Av) is calculated.
High CMRR (> 40 dB) indicates good common-mode rejection.
For this we priorly need to calculate gain with theoretical values. <br>
gain = Av= -gm*Rd 
where gm= (2Id)/Vov = 2.27ms <br>
Av= -2.27ms * 1.9k = -4.31 V/V <br>
as we know Av= 20Log(vout/Vin)<br>
in dB scale theoretical gain is 11.59dB <br>
![Image](https://github.com/user-attachments/assets/271dcf90-3b47-4dbe-904e-c07e6fab208c)
![Image](https://github.com/user-attachments/assets/18d98aa1-a8fe-4577-b13c-1c12737a5720)
![Image](https://github.com/user-attachments/assets/fcd2e606-cfc3-4326-9bc8-bdb895e30707)


|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 13.92dB      | 13.01dB         |
|Av(in V/V)     | 4.97         | 4.47            |

<br>

## CIRCUIT 2 : Current Source-Loaded Differential Pair:<br>
### DC Analysis :<br>
![Image](https://github.com/user-attachments/assets/0d4ea0cd-38be-4e7a-9713-af96ea5cc199)



The transistor to operate in saturation region ,<br>
Vgs>Vth, <br>
Vds> Vov <br>

### Transient Analysis :<br>
![Image](https://github.com/user-attachments/assets/ddd3a12b-bfb4-4b07-ab88-8eac40e8777f)

##### For Amplitude = 50mV; <br>
#### When Vincm = 0V :
#### FOR 50mV AMPLITUDE :
|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Vincm(min)     | 0.86V        | 0V              |
|Vincm(max)     | 1.76V        | 1.9V            |

<br>
### AC Analysis:<br>

![Image](https://github.com/user-attachments/assets/c5758e33-5f00-47a0-a8f6-9396a4857f4d)
![Image](https://github.com/user-attachments/assets/f9a88a16-9f87-48f9-862a-b9c76dbd3d7f)
![Image](https://github.com/user-attachments/assets/422b7377-e74e-4594-81eb-f08fb307f261)

gain = Av= -gm*Rd 
where gm= (2Id)/Vov = 2.27ms <br>
Av= -2.27ms * 1.9k = -4.31 V/V <br>
as we know Av= 20Log(vout/Vin)<br>
in dB scale theoretical gain is 11.59dB <br>

|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 13.92dB      | 13.5dB          |
|Av(in V/V)     | 4.97         | 4.73            |

<br>

## CIRCUIT 3 :  Simple Current Source Differential Pair:<br>
### DC Analysis :<br>
The transistor to operate in saturation region ,<br>
Vgs>Vth, <br>
Vds> Vov <br>
![Image](https://github.com/user-attachments/assets/e9df5883-8c11-4603-881b-15ae13c1b1e8)

### Transient Analysis <br>
#### FOR 50mV AMPLITUDE :
![Image](https://github.com/user-attachments/assets/7cd07614-0013-4419-beb8-e26910ced1d0)
|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Vincm(min)     | 0.86V        | 0.66V           |
|Vincm(max)     | 1.76V        | 2.50V           |

<br>
### AC Analysis: <br>

![Image](https://github.com/user-attachments/assets/b55890bc-58ac-43a8-985b-e0e0288bd3b4)
![Image](https://github.com/user-attachments/assets/e2be45e3-83eb-4d7a-8b5d-f11b206ce569)
![Image](https://github.com/user-attachments/assets/f4df02fe-d1a7-4fb3-a7a3-c0e56387db7a)

<br>


|Parameter      |Theory value  | Practical value |
|---------------|--------------|-----------------|
|Av(in dB)      | 13.92dB      | 20 dB           |
|Av(in V/V)     | 4.97         | 10              |













