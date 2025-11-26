# GENERATION-AND-DETECTION-OF-FM
## AIM:
To write a program for Frequency Modulation and Demodulation using SCILAB and to observe and measure the frequency deviation and the modulation index of FM.

## EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

## THEORY
  Frequency modulation is a type of modulation in which the frequency of the high frequency (carrier) is varied in accordance with the instantaneous value of the modulating signal.
  
  #### FREQUENCY DEVIATION Δf  and MODULATION INDEX m f :
  
  The frequency deviation Δf represents the maximum shift between the  modulated signal
  frequency, over and under the frequency of the carrier.
  
  We define modulation index m f the ratio between Δf and the modulating frequency
  m= Δf / fm


#### FREQUENCY MODULATION GENERATION:
  The circuits used to generate a frequency modulation must vary the frequency of a high frequency signal (carrier) as function of the amplitude of a low frequency signal (modulating signal). In practice there are two main methods used to generate FM.

## ALGORITHM
  1.	Define Parameters:
     
      •	Fs: Sampling frequency.
      •	T: Duration of the signal.
      •	Fc: Carrier frequency.
      •	Fm: Frequency of the modulating signal.
      •	Beta: Modulation index, which controls the extent of frequency deviation.
  2.	Generate Signals:
     
      •	modulating_signal: Sinusoidal signal used for modulation.
      •	carrier_signal: The high-frequency carrier signal.
      •	modulated_signal: FM modulated signal calculated by varying the carrier frequency according to the modulating signal.
      
  3.	FM Modulation:
     
      •	Modulated_signal is obtained by modulating the carrier signal with the modulating signal.
 
  4.	FM Demodulation:
     
      •	Differentiation: Computes the derivative of the modulated signal to extract frequency variations.
      •	Envelope Detection: Takes the absolute value to retrieve the envelope of the signal.
      •	Low-pass Filtering: Applies a Butterworth low-pass filter to smooth the envelope and recover the original modulating signal.
      
  5.	Visualization:
      
      •	Plots the modulating signal, carrier signal, FM modulated signal, and demodulated signal for analysis.


## PROCEDURE

    •	Refer Algorithms and write code for the experiment.
    •	Open SCILAB in System
    •	Type your code in New Editor
    •	Save the file
    •	Execute the code
    •	If any Error, correct it in code and execute again
    Verify the generated waveform using Tabulation and Model Waveform

## MODEL GRAPH:
<img width="512" height="365" alt="image" src="https://github.com/user-attachments/assets/dfe6bc64-2b6f-4afa-ae79-95391859ab04" />

## PROGRAM
~~~
clc;
clear;
close;

Ac = 14;          
fc = 6530;         
Am = 7;         
fm = 653;        
fs = 653000;       
beta = 3.6;        
t = 0:1/fs:2/fm;   
Em = Am * cos(2 * %pi * fm * t);
subplot(4,1,1);
plot(t, Em);
xlabel("Time (s)");
ylabel("Amplitude");
title("Modulating Signal");

Ec = Ac * cos(2 * %pi * fc * t);
subplot(4,1,2);
plot(t, Ec);
xlabel("Time (s)");
ylabel("Amplitude");
title("Carrier Signal");

Efm = Ac * cos(2 * %pi * fc * t + beta * sin(2 * %pi * fm * t));
subplot(4,1,3);
plot(t, Efm);
xlabel("Time (s)");
ylabel("Amplitude");
title("FM Modulated Signal");
y = diff(Efm);              
y = [y y($)];                
demod = abs(y);              
demod = demod - mean(demod);
demod = demod / max(abs(demod)) * max(Em);  
subplot(4,1,4);
plot(t, demod);
xlabel("Time (s)");
ylabel("Amplitude");
title("Demodulated Signal");
~~~
## TABULATION

![WhatsApp Image 2025-11-18 at 21 05 15_3b10c1c7](https://github.com/user-attachments/assets/9a621dcb-3161-4d6c-83df-bd97998fc732)

## OUTPUT

<img width="1291" height="788" alt="image" src="https://github.com/user-attachments/assets/6fd60333-0127-4a00-84d5-de5da01298be" />

## RESULT
Thus the frequency modulation and demodulation is successfully done and the output is experimentally verified.
