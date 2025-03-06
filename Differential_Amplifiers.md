# Differential Amplifiers
*A differential amplifier is a type of electronic amplifier that amplifies the difference between two input signals while rejecting any signals that are common to both inputs. This makes it extremely useful in applications where noise and interference need to be minimized, such as in sensor circuits and audio processing.*

## Aim: 
### ***Design a Differential Amplifier for the following specifications Vdd = 3.2V, P <= 2.8mW, Vicm = 1.6V, Vocm = 1.7V, Vp = 0.6V. Perform DC Analysis, Transient Analysis and Frequency Response also extract the Required Parameters.***
![image](https://github.com/user-attachments/assets/7bda4d64-bc04-4ccf-9c68-0bda41cb7287)
- Iss = P/V = (2.8mW)/(3.2V) = 0.875mA

- Id1 = Id2 = Iss/2 = 0.437mA

- Rss = Vp/Iss = 0.6V/0.875mA = 685.71 Ohms

- Rd = (Vdd-Vocm)/Id1 = (3.2-1.7)/(0.437mA) = 3.432K Ohms

***Since we have found out all the required Parameters now we Rig up the Circuit in LTspice***
### Procedure
- *Open LTspice and import the tsmc018.lib file before building up the circuit.*
- *Make sure that the file must be in the same folder as the experiment file*
- *Use the (.t) option in the toolbar and type **.lib tsmc018.lib** to import the library of that file*
- *Select the Rd and Rs with accurate Values and Select NMOS4*
- *Rename the MOSFET's as CMOSN* 
- *To perform the DC analsyis we must select the **Configure Analysis** Option in toolbar and select **DC op pnt** find the **Id** by adjusting the length and width of the CMOSN*
- *To perform the Transient analsyis we must select the **Configure Analysis** Option in toolbar and select **Transient** set the operating point such as Stop time **5ms** find the **Gain** by finding out the **Vin** and **Vout** from the waveform*
-  *To perform the AC analsyis we must select the **Configure Analysis** Option in toolbar and select **AC analysis** select the operating points like Type of sweep as **decade**, Number of points per decade as **20**, Start and Stop Frequency from **0.1 to 1T Hz***

## Circuit 1 
![image](https://github.com/user-attachments/assets/905ddfcd-4844-4c8b-a318-b1e078060ebd)
***After building up the circuit perform the DC analysis, Transient Analsyis and AC analysis find the frequency response***
## DC Analysis
- *After setting the voltage source as specified we must find the appropriate W and L values for CMOSN**
- *The Value of L is **180nm***
- *The Value of W is **2.53223977um***
- *The Value of Id for these specification is **0.4375mA***
- *The Value of Iss for this specification is **0.875mA***
- *The Value of Vocm1, Vocm2 for this specification is **1.7V***
  
![image](https://github.com/user-attachments/assets/db02ec9a-9aaa-4f3a-86b6-9c6e073f9bd3)

## Transient Analysis
*The First voltage source near gate of M1 should be changed from DC to sine wave source with **DC Offset** as **1.6V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

*The Second voltage source near gate of M2 should be changed from DC to sine wave source with **DC Offset** as **1.6V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

***To perform Transient Analysis we must set the stop time for 5ms and the appropriate waveform is given by,***

*Select the probe at **output node** for output waveform and at **1.6V Voltage source** for input waveform*

![image](https://github.com/user-attachments/assets/eb2dfa6b-69fa-487b-8170-a732747d7a8c)

- Vout = 0.0668V
- Vin = 0.04833V
- Gain = (Vout)/(Vin) = (0.0668)/(0.04833) = 1.382164

*We observe that the **input** is **180 degree** out-of-phase with **output***

## AC Analysis
***To perform AC analysis we must set the operating point first they are shown below***
- *Type of sweep as **decade***
- *Number of points per decade as **20***
- *Start Frequency as **0.1 Hz***
- *Stop Frequency as **1T Hz***

*Select the probe at **Output node***

![image](https://github.com/user-attachments/assets/d042ea7d-feff-4b8f-ae7b-fe03cf449f8d)

## Circuit 2
![image](https://github.com/user-attachments/assets/0313c41c-ac67-498e-9946-bcad84fdee6d)

***Replace the Resistor Rss by a current source Iss***
- *The value of Iss is **0.875mA***

***After building up the circuit perform the DC analysis, Transient Analsyis and AC analysis find the frequency response***
## DC Analysis 
- *The Value of L is **180nm***
- *The Value of W is **2.53223977um***
- *The Value of Id for these specification is **0.4375mA***
- *The Value of Iss for this specification is **0.875mA***
- *The Value of Vocm1, Vocm2 for this specification is **1.7V***

![image](https://github.com/user-attachments/assets/58ae1520-3283-4e59-a3ca-a5682b821906)

## Transient Analysis
*The First voltage source near gate of M1 should be changed from DC to sine wave source with **DC Offset** as **1.6V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

*The Second voltage source near gate of M2 should be changed from DC to sine wave source with **DC Offset** as **1.6V** and **Amplitude** as **-50m** and **Frequency** as **1K Hz***

***To perform Transient Analysis we must set the stop time for 5ms and the appropriate waveform is given by,***

*Select the probe at **output node** for output waveform and at **1.6V Voltage source** for input waveform*

![image](https://github.com/user-attachments/assets/d298ee12-add6-4186-874b-c1baeca75c06)

- Vout = 0.16627V
- Vin = 0.04992V
- Gain = (Vout)/(Vin) = (0.16627)/(0.04992) = 3.33072

*We observe that the **input** is **180 degree** out-of-phase with **output***

## AC Analysis
***To perform AC analysis we must set the operating point first they are shown below***
- *Type of sweep as **decade***
- *Number of points per decade as **20***
- *Start Frequency as **0.1 Hz***
- *Stop Frequency as **1T Hz***

*Select the probe at **Output node***



## Circuit 3
![image](https://github.com/user-attachments/assets/e0590c00-6083-4950-a1ee-db2810e6e1bf)

***Replace the Resistor Rss by NMOS(M3)***
- *The value of L is **180nm***
- *The value of W is **2.53223977um***
- *The value of gate i.e Vb is **1.429730V***

***After building up the circuit perform the DC analysis, Transient Analsyis and AC analysis find the frequency response***
## DC Analysis 
- *The Value of L is **180nm**(M1 and M2)*
- *The Value of W is **2.53223977um**(M1 and M2)*
- *The Value of Id for these specification is **0.4375mA***
- *The Value of Iss for this specification is **0.875mA***
- *The Value of Vocm1, Vocm2 for this specification is **1.7V***

![image](https://github.com/user-attachments/assets/ed0f70af-6f0b-4e9c-bcc5-0bceb8797570)

## Transient Analysis
*The First voltage source near gate of M1 should be changed from DC to sine wave source with **DC Offset** as **1.6V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

*The Second voltage source near gate of M2 should be changed from DC to sine wave source with **DC Offset** as **1.6V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

***To perform Transient Analysis we must set the stop time for 5ms and the appropriate waveform is given by,***

*Select the probe at **output node** for output waveform and at **1.6V Voltage source** for input waveform*

![image](https://github.com/user-attachments/assets/3ba08bfc-3ae0-483f-a189-9e8f713974ee)

- Vout = 0.013875V
- Vin = 0.04864V
- Gain = (Vout)/(Vin) = (0.013875)/(0.04864) = 0.285259

*We observe that the **input** is **180 degree** out-of-phase with **output***

## AC Analysis
***To perform AC analysis we must set the operating point first they are shown below***
- *Type of sweep as **decade***
- *Number of points per decade as **20***
- *Start Frequency as **0.1 Hz***
- *Stop Frequency as **1T Hz***

*Select the probe at **Output node***

![image](https://github.com/user-attachments/assets/d58c5b73-7d24-4194-9369-175eb504cf61)

## Conclusion
### *In Circuit 1,* 
- *It is difficult to maintain stable current and it is highly dependent on supply voltage variations*
### *In Circuit 2,* 
- *Instead of using a resistor, a dedicated current source can be used to provide a constant current*
- *A constant current source ensures that the differential pair maintains better common-mode rejection*
- *The current becomes independent of supply voltage variations*
- *Since the impedance at the tail node is increased, the gain of the differential amplifier improves*
### *In Circuit 3,*
- *Instead of using a current source, an NMOS transistor operating in saturation (acting as a current source) can be used to generate the current*
- *An NMOS transistor in saturation has a much higher output resistance compared to a resistor or simple current source, improving gain*
- *An active current source can be designed to consume minimal power while maintaining a stable current*
- *Unlike resistors, NMOS-based current sources work well at low supply voltages, making them ideal for modern low-power applications*
