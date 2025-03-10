# LIC-Lab
## Overview:


A MOS Differential Amplifier is a key circuit in analog electronics, used for signal amplification, common-mode rejection, and noise suppression. It consists of two matched MOSFETs, a current source, and load resistors.

**Circuit Diagram:**
![lab](https://github.com/user-attachments/assets/be962a12-34c9-41c0-8548-62a354762fbf)


**Working Principle**
- Differential Input: The circuit amplifies the difference between the two input voltages (V_IN1 - V_IN2).
- Current Source Biasing: The total bias current (I_BIAS) is constant, ensuring stable operation.
- Output Voltages: The amplified signals appear at V_OUT1 and V_OUT2.
![lab2](https://github.com/user-attachments/assets/383b59d4-8358-4bc2-ba90-7f8b2e2400f7)


The sum of the two drain currents ID1 and ID2 must equal IBIAS. We also know that the two drain currents are equal because, in this idealized analysis, both halves of the circuit are identical. Thus,

![lab3](https://github.com/user-attachments/assets/acd70b25-332d-41f2-b0e4-30eb1ea6e6f7)


Let’s assume for the moment that the transistors are in saturation. The equation for saturation-mode drain current is the following:
![lab4](https://github.com/user-attachments/assets/7a25c09d-75e4-470d-9303-e716ef2a5549)


 The drain current is already established (by the current source) and the gates are tied to the ground node; this means that the source voltage will settle on whatever value creates a gate-to-source voltage (VGS) corresponding to a drain current of IBIAS/2.
## Components used:


1. NMOS Transistor
2. Voltage Source
3. Resistors 
4. Ground
5. CONNECTING wires
## Procedure:
 •	Open LTspice  and create a new schematic by selecting File > New Schematic.

•	Select the Components required to design a Common Source Amplifier  such as NMOS,voltage source, wire, and ground. 

•	Connect the components as shown in the above fig.1

•	Set Component Values by Right-clicking on each component to set their values 

•	Go to edit option select spice directive and attach tsmc018.lib file

•	To run the simulation click on  run button
##

•	To get DC Operating Point Analysis
1.	Click on Simulate > confiure analysis
2.	Select DC op pnt and click OK
3.	Place the .op directive on your schematic and stop time as 3m
4.	Run the Simulation
5.	Click the Run button (the running man icon)
6.	The DC operating point voltages and currents will be displayed in a table
   ##

•	To get AC operating Point analysis
1.	Right-click on the voltage source and select sine function set AC Amplitude to 50mv, frequency to 1KHz, DC offset to 1v
2.	Click on Simulate > configure analysis
3.	Select AC Analysis.
4.	Enter the type of sweep decade, number of points 20,  start frequency 0.1 Hz, and stop frequency 1T Hz.
5.	Click OK and place the .ac directive on your schematic.
6.	Run the Simulation
7.	Click the Run button
8.	The AC analysis results will be displayed to get the waveform click on input/output voltage.
##

•	To get Transient Analysis
1.	Click on Simulate > configure analysis
2.	Select Transient and enter the stop time (5milliseconds).
3.	Click OK and place the .tran directive on your schematic.
4.	Run the Simulation:
5.	Click the Run button.
6.	The transient analysis results will be displayed  to get waveform  click on output /input volatges.
