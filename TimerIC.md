#  Monostable and Astable Multivibrator using 555 Timer IC

---

##  Project Overview

This project demonstrates the **design, simulation, and analysis** of Monostable and Astable Multivibrator circuits using the popular **555 Timer IC**. Both configurations are used to generate timed pulses, which are essential in digital logic, timer circuits, and oscillators.

The project involves:
- Designing monostable and astable circuits
- Simulating their behavior in virtual environments
- Observing and documenting the waveform outputs
- Creating a pulse of **0.5 ms width**
- Utilizing differentiator and clipper circuits for trigger generation

---

##  Aim

> To generate a pulse of **0.5 ms** duration using a **555 Timer IC** in both **monostable** and **astable** modes.

---

##  Theoretical Background

### 1. Monostable Multivibrator
- Has **one stable** and **one quasi-stable** state.
- Requires an **external trigger** to change the state.
- After a specific time, it reverts to the stable state.

**Time period (pulse width)**:  
\[
T = 1.1 \times R \times C
\]

- **R** is the resistance in ohms.
- **C** is the capacitance in farads.
- Output is HIGH for `T` seconds after a trigger pulse.

### 2. Astable Multivibrator
- A free-running oscillator (no stable state).
- Continuously alternates between HIGH and LOW states.
- Used to generate square or rectangular waves.

**Time period**:  
\[
T = 0.693 \times (R_a + 2R_b) \times C
\]

**Duty Cycle**:
\[
\text{D} = \frac{R_a + R_b}{R_a + 2R_b} \times 100\%
\]

Where:
- Ra = Resistor connected between Vcc and discharge pin
- Rb = Resistor between discharge pin and threshold pin
- C = Timing capacitor

### 3. Differentiator Circuit
- A capacitor-resistor circuit that responds to **changes in voltage**.
- Produces **short pulses** on rising/falling edges.
- Helps in extracting trigger pulses for monostable circuits.

### 4. Negative Clipper
- Removes negative portions of an input signal.
- Ensures only the **positive edge triggers** the monostable.

---

##  Components Used

| Component           | Value             |
|--------------------|------------------|
| NE555 Timer IC     | 2                |
| Resistors (Ra, Rb) | 3.3kΩ, 6.8kΩ     |
| Capacitor (C)      | 0.1 µF           |
| Inverter           | Logic NOT Gate   |
| Oscilloscope       | For waveform view|
| Breadboard/Simulator | Multisim / Proteus / Tinkercad |

---

##  Circuit Diagrams

###  Monostable Multivibrator:
![Image](https://github.com/user-attachments/assets/e19694d0-2e06-4fd7-a29d-96534ac82ac3)

###  Full Setup: Astable + Differentiator + Clipper + Monostable
![Image](https://github.com/user-attachments/assets/2ebc6bbe-ddc1-4ba9-ae83-1b65d9013ee1)

---

##  Output Waveforms

###  Case 1: Standard Output from Astable to Monostable
- Input Frequency: ~1 kHz
- Monostable Pulse Width: 0.5 ms
- Output Signal: Rectangular pulse
![Waveform 1]![Image](https://github.com/user-attachments/assets/ff36e141-de01-447d-91d6-55f27d91dd90)
![Image](https://github.com/user-attachments/assets/b6384622-2baa-454d-b9af-bf45aeb81427)
![Image](https://github.com/user-attachments/assets/911097b3-0c0d-406a-8c3f-16cab810ab64)
![Image](https://github.com/user-attachments/assets/65e87bcd-e427-4201-ba35-06333d0c1661)
![Image](https://github.com/user-attachments/assets/d8efc288-33d6-42a8-883f-5d70b5097e3e)

---

###  Case 2: High-Speed Operation (Low R, C)
- Ra = 1kΩ, Rb = 1kΩ, C = 0.01µF
- Observed pulse widths: ~0.05 ms


---

###  Case 3: Inverted Output for OFF > ON
- Output Inverted using NOT gate
- Achieved OFF = 0.4 ms, ON = 0.1 ms


---

##  Simulation Procedure

### Using Virtual Labs / Proteus / Tinkercad:
1. **Connect circuit** as per diagrams using the 555 timer.
2. Set values:
   - Monostable: R = 4.5kΩ, C = 0.1µF
   - Astable: Ra = 3.3kΩ, Rb = 6.8kΩ, C = 0.1µF
3. Use waveform generator or differentiator + clipper as trigger source.
4. Observe and capture waveforms using oscilloscope tool.
5. Measure time intervals using cursors.
6. Repeat with different values for RC to verify time period formula.

---

##  Calculations

### Monostable Time Duration:
\[
T = 1.1 \times R \times C = 1.1 \times 4.5k\Omega \times 0.1\mu F = 0.495 \, ms
\]

### Astable Time Period:
\[
T = 0.693 \times (Ra + 2Rb) \times C = 0.693 \times (3.3k + 2 \times 6.8k) \times 0.1\mu F = 1.27 \, ms
\]

---

##  Results and Observations

| **Test Case** | **Configuration**              | **ON Time** | **OFF Time** | **Remarks**                      |
|---------------|-------------------------------|-------------|--------------|----------------------------------|
| Case 1        | Standard Astable + Monostable | 0.2 ms      | 0.3 ms       | Good for basic square wave gen. |
| Case 2        | High-speed astable setup      | 0.05 ms     | 0.05 ms      | Stable only with precision parts|
| Case 3        | Output Inversion              | 0.1 ms      | 0.4 ms       | Achieves longer OFF duration    |

---

##  Inference

- Monostable multivibrator produces a **single fixed-width pulse** on trigger.
- Astable multivibrator creates a **continuous square wave** without trigger.
- Output duration is highly dependent on **RC constants**.
- 555 Timer provides a cost-effective solution for waveform generation.
- Additional shaping circuits like differentiators and clippers are essential for clean triggering in practical systems.
- Output waveform characteristics match theoretical predictions.

---

##  Learnings

- Designing timers and oscillators using analog ICs.
- Using passive components to control pulse width.
- Role of edge detection in digital systems.
- Waveform measurement and analysis using virtual tools.
- Importance of circuit simulation before hardware testing.








>  This project was created for academic purposes and demonstrates fundamental timer circuit design using 555 IC.




