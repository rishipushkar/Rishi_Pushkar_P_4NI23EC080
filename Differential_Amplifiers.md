# Differential Amplifiers
A differential amplifier is a type of electronic amplifier that amplifies the difference between two input signals while rejecting any signals that are common to both inputs. This makes it extremely useful in applications where noise and interference need to be minimized, such as in sensor circuits and audio processing.

## Aim: Design a Differential Amplifier for the following specifications Vdd = 3.2V, P <= 2.8mW, Vicm = 1.6V, Vocm = 1.7V, Vp = 0.6V. Perform DC Analysis, Transient Analysis and Frequency Response also extract the Required Parameters.
![image](https://github.com/user-attachments/assets/7bda4d64-bc04-4ccf-9c68-0bda41cb7287)
Iss = P/V = (2.8mW)/(3.2V) = 0.875mA

Id1 = Id2 = Iss/2 = 0.437mA

Rss = Vp/Iss = 0.6V/0.875mA = 685.71 Ohms

Rd = (Vdd-Vocm)/Id1 = (3.2-1.7)/(0.437mA) = 3.432K Ohms

