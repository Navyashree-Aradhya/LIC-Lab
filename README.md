# LIC-Lab
## Overview:
##  i . Aim:
Design and analyse the differential amplifier for the following specifications:



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

## circuit 1:(with R<sub>SS</sub>)
![circuit1](https://github.com/user-attachments/assets/e89b8bd8-25d9-458b-bf3c-7af163f7dfae)
### Calculation:
* P=1mW
* I<sub>SS</sub> = P/V = 1mW/2V  <table><td>=0.5mA</td><table>
* I<sub>D1</sub> = I<sub>D2</sub> = I<sub>SS</sub>/2  <table><td>=0.25mA</td><table> 
* V<sub>GS</sub> = V<sub>incm</sub> - V<sub>P</sub> = 1-0.4  <table><td>=0.6V</td><table>
* R<sub>D</sub> = V<sub>outcm</sub>-V<sub>DD</sub>/ I<sub>D</sub> = 1.1-2/0.25m <table><td>=3.6Kohm</td><table> 
* R<sub>SS</sub> = V<sub>p</sub>/ I<sub>SS</sub> = 0.4/0.5m <table><td>=0.8Kohm</td><table> 
* g<sub>m</sub> = 2I<sub>D</sub>/V<subOV</sub> = 2(0.25m)/0.6-0.36 <table><td>=2.08m</td><table>
* A<sub>V</sub> = -g<sub>m</sub>R<sub>D</sub> = -2.08m(3.6K) <table><td>=7.488V/V</td><table> 
* A<sub>V</sub>dB = 20log(A<sub>V</sub>) = 20log(7.488) <table><td>=17.48</td><table>
* V<sub>incm(min)</sub> = V<sub>TH</sub> + V<sub>P</sub> = 0.36 + 0.4  <table><td>=0.76</td><table> 
* V<sub>incm(max)</sub> = V<sub>DD</sub> - I<sub>D</sub>R<sub>D</sub> + V<sub>TH</sub> = 2-(0.25m)(3.6K)+0.36 <table><td>=1.46V</td><table> 
* imput max swing = V<sub>incm(min)</sub> - V<sub>incm(max)</sub> <table><td>=0.7V</td><table> 
* V<sub>outcm(min)</sub> = V<sub>OV</sub> + V<sub>p</sub> <table><td>=0.64V</td><table>
* V<sub>outcm(max)</sub> = V<sub>DD</sub> - I<sub>D</sub>R<sub>D</sub> <table><td>=1.1V</td><table> 
* output max swing = V<sub>outcm(min)</sub> - V<sub>outcm(max)</sub> <table><td>=0.46V</td><table>
  <br>
  ### Simulation Result :
  1.DC analysis:\
![circuit1 2](https://github.com/user-attachments/assets/3ca16670-97cc-416c-b0a4-3982d30e30e8)
![circuit 1 221](https://github.com/user-attachments/assets/ff90e7c4-5291-437d-8b45-17fc399c0302)
+ V<sub>out1</sub> = V<sub><out2</sub> = 1.1V.
* I<sub>D</sub> = 0.25mA which satisfy the condition P<=1mW.
* V<sub>P</sub> = 0.4V.
* I<sub>SS</sub> = 0.5mA.
* Q point = (V<sub>DS</sub>, I<sub>D</sub>) = (0.7V,0.25mA)
<br>

2.Transient Analysis: for Vin= 1V and varying input amplitude
![transient analysis](https://github.com/user-attachments/assets/9b25717c-a354-4825-9cbb-0c7897a17c18)

* input peak to peak volatge 200mV.
* Distortion occurs
![Screenshot (26)](https://github.com/user-attachments/assets/e544fbc0-f464-44a1-9435-b7d1fde853b0)
* input peak to peak voltage = 100mV (linear amplifier range).
* output peak to peak voltage = 1.766V.
* A<sub>V</sub> = 1.766V/100mV = 0.01766m = 17.66V/V.
Hence if the Amplitude increases distortion ocuurs. To maintain the circuit as linear amplifier set the input amplitude volatge and between minimum to maximum input common mode volatge properly otherwise circuit enters to cut off region and distortion occurs therefore it no longer will be the linear amplifier.

<br>

***To Calculate Output maximum swing***
![swing](https://github.com/user-attachments/assets/a5a7e177-9394-4d17-aeed-a98224065952)
Here the Output is started from 1.0991V to 1.5358V. Therefore the maximum output swing is 1.5358-1.0991=0.4367 which matches the theoritical value 0.46V.
<br>
![swing2](https://github.com/user-attachments/assets/8105514f-4898-4879-8b0f-03c853c53396)
Here the input is started from 1V to 1.0494V. Therefore The maximum input swing is 0.0494V.
<br>
- The Differential Gain is given by maximum output swing/maximum input swing = 18.92dB.


<br>

3.AC analysis :
   ![Screenshot (27)](https://github.com/user-attachments/assets/bfa9e4e8-1644-4654-93f0-d16ec97b28e0)

  * 3dB Gain= 16.5dB
  * 3dB gain bandwidth = 0 to 3.839GHz.
  * CMRR = Differential gain (g<sub>m</sub>R<sub>D</sub>) / Common mode gain (V<sub>out</sub>/V<sub>incm</sub>) = 12.5.

<br>

### Inference:
1.current varies with respect to width.\
2.To get the expected output vary R<sub>D</sub> value inversly.\
3.Mosfet should be in the saturation region.\
4.Both the transistors and resistors should be identical.\
5.By connecting both the transistors to a single R<sub>SS</sub>, current is kept constant. ultimately this type of connection helps to maintain the constant current throughout the circuit by acting as a feedback network even if there are any small changes in the current flowing through the transistors.\
6.Noise cancelation which is CMRR that is it will cancel the noise by taking the difference of input signals by cancelling the common mode signals.\
7.from dc analysis we get operating point,dirfferential gain, maximum input and output swing.\
8.form transient analysis we get input and output peak to peak values so that we can calculate the gain of the circuit.\
9.from ac analysis we get 3dB gain and CMRR of the circuit.\




