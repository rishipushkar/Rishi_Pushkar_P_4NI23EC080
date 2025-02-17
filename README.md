# Analysis of CS Amplifier  

## Introduction  

The CS amplifier is a basic building block of analog electronics, for voltage amplification purposes.  

### Question  

This paper examines the behavior of a CS amplifier whose 180nm MOSFET is used as a device component and whose supply voltage (Vdd) is set to 1.8V. The objective is to determine the.  

- *Drain current (Id)*  
- *Compute the MOSFET width (W)*  
- *Perform AC and transient analyses*  

To examine the amplifier's behavior.  

---

## Circuit Specifications  

The given specifications for our amplifier are:  

- *Channel Length (L)* = 180nm.  
- *Supply Voltage (Vdd)* = 1.8V.  
- *Gate Voltage (Vg)* = 0.6V (DC offset)  
- *Power Budget* = 50μW.  
- *Drain Current (Id)* = 27μA (calculated using power constraints)  
- *MOSFET Width (W)* = 1.08μm.  

Additionally, the gate voltage is modulated using a sinusoidal input signal:  

- *DC Offset* = 0.6V.  
- *Amplitude* = 50mV.  
- *Frequency* = 1kHz.  
- *AC Amplitude* = 1.  

---

## Calculation of Width (W)  

The *Drain current (Id)* Can be determined:  

P = V * I

I = P / V

I = 50μW / 1.8V

I = 27μA


We determine the *MOSFET width (W) = 1.08μm* in order to obtain the target operating conditions and good current conduction.  

![image](https://github.com/user-attachments/assets/13e5cd7f-c06d-421d-a64d-05496b7bda50)

![image](https://github.com/user-attachments/assets/c4bc361a-b3ee-42fa-a1c0-41cd900ac136)


---

## AC Analysis  

The *AC analysis* helps us study the frequency response of the amplifier. The parameters used for this simulation are:  

- *Sweep Type* = Decade.  
- *Number of Points per Decade* = 20.  
- *Start Frequency* = 0.1 Hz.  
- *Stop Frequency* = 1THz.  

A probe is placed at the *Drain (output)* and another at *Vg (input)* to visualize the frequency response.  

This helps in understanding the amplifier's gain and bandwidth.  

![image](https://github.com/user-attachments/assets/e652c8ef-85d1-4d3c-8be1-e975900718a0)


---

## Transient Analysis  

To observe the amplifier's behavior over time, a *Transient analysis* is performed with the following parameter:  

- *Stop Time* = 5ms.  

This enables us to investigate the response of the amplifier to the *Sinusoidal input signal* in the time domain, capturing its transient performance.  

![image](https://github.com/user-attachments/assets/07d6c26b-4fcd-4358-9c1c-e6ae8313b2f2)

![image](https://github.com/user-attachments/assets/ff9446c6-5425-4254-ad72-b6ec566da6be)

![image](https://github.com/user-attachments/assets/18831a86-208e-45dc-b764-702e4813f23f)


---

## Inference and Observations  

### 1. Drain Current and Width Calculation  

- Based on the power budget of 50μW, the *Drain current (Id) was determined to be 27μA*, by which the MOSFET is guaranteed to work efficiently in saturation regime.  
- The *Width of the MOSFET was calculated to be 1.08μm*, which enables the necessary current flow without compromising the desired operating conditions.  

### 2. AC Analysis Observations  

- The *Frequency response graph* will provide insight into the amplifier's *Gain and bandwidth*.  
- The *Gain remains constant at low frequencies*, however, it begins to decay beyond a particular cutoff frequency, referring to the cutoff bandwidth of the amplifier.  
- The *Gain at mid-band frequencies* estimates the ability of the amplifier to boost a given input signal, which is an essential parameter, in signal processing tasks.  

### 3. Transient Analysis Observations  

- The transient response will show the behavior of an amplifier when a *1kHz sinusoidal input* is applied over time.  
- When properly conceived, the *output waveform should be an amplified and inverted version of the input*, confirming that the amplifier is working as expected.  
- Any *distortions in the waveform* could indicate *Nonlinearities in the MOSFET operation*, possibly due to improper biasing or mismatched parameters.

---
## Circuit 2

# Inverted CS Amplifier Analysis

## Introduction

The objective of this report is to evaluate the inverting behavior of a CS amplifier when it operates on both DC and AC sources. 

## Question

The supplied supply voltage is **1.8V**, and the dissipation of power is **50μW**. Given a gate voltage (**VG**) of **0.7V**, the target voltage is used to determine the **DC operating point (ID)**. Moreover, an **AC analysis** is carried out with a sinusoidal input voltage, and then analyzed using shifted transients to determine the time domain.

---

## NMOS and PMOS Specifications

### **PMOS Configuration:**

- **Source:** Connected to supply (**1.8V**)  
- **Gate:** Connected to **0.7V**  
- **Drain:** Connected to NMOS drain.  

### **NMOS Configuration:**

- **Source:** Grounded.  
- **Gate:** Connected to **0.7V**.  
- **Drain:** Connected to PMOS drain.  

### **Chosen Transistor Dimensions:**

PMOS (W/L): ___ / ___ 

NMOS (W/L): ___ / ___

## **DC Analysis**

Our approach in conducting DC analysis involves identifying the quiescent operating point (ID) and node voltages that are required to operate the MOSFET.

- **Supply Voltage (VDD)**: 1.8V  
- **Gate Voltage (VG)**: 0.7V  
- **Power Budget (P)**: 50μW  

P = VDD * ID

ID = P/VDD

ID = 50μW / 1.8V

ID = 27μA

## **AC Analysis**

A sinusoidal input is included in the AC analysis through a modification of gate voltage.

**Sinusoidal Input Voltage**

- DC Offset: 0.7V  
- Amplitude: 50mV  
- Frequency: 1kHz

**Frequency Sweep Parameters**

- Type: Decade  
- Sweeps per Decade: 20  
- Start Frequency: 0.1Hz  
- Stop Frequency: 1THz  

By analyzing the AC, one can determine gain, bandwidth, phase, and other characteristics of the amplifier's frequency response.

Graph

## **Transient Analysis**

By examining the transient response of the amplifier, it is possible to determine its behavior over time when subjected to the sinusoidal input.

**Parameters**

- Stop Time: 5m (5 milliseconds)

The transient analysis provides information about the amplifier's time-domain behavior, such as distortion, settling time, and waveform reproduction.

Graph

## **Inference**

**DC Analysis**

- The drain current (ID) required is approximately 27.78A, which should ensure the MOSFET operates correctly at its desired location.
- The conditions of biasing offer a reliable means of amplification.

**AC Analysis**

- The gain response and bandwidth can be analyzed using the AC sweep.
- The amplifier's performance across a broad frequency range, including its cutoff frequencies and phase behavior, will be taken into account when determining its suitability for various applications.

**Transient Analysis**

- The input waveform is accurately reproduced by the amplifier, as demonstrated.
