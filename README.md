# EXP 3 : IIR-CHEBYSHEV-FITER-DESIGN

## AIM: 

 To design an IIR Chebyshev filter  using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (LPF): 
```
clear;
Fs = 5000;  fc = 1500;
b = [0.0929 0.2787 0.2787 0.0929];
a = [1 -0.5772 0.4218 -0.0561];
[H, fn] = frmag(b, a, 512);
f = fn * Fs;
clf;
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I LPF (Order 3)");
xgrid();
disp(b,"b=");
disp(a,"a=");
```
## PROGRAM (HPF): 
```
clear;
Fs = 5000; fc = 1500;
b = [0.4218 -0.5772 0.2787 -0.0929];
a = [1 -0.5772 0.4218 -0.0561];
[H, fn] = frmag(b, a, 512);
f = fn * Fs;
clf;
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I High Pass Filter (Order 3)");
xgrid();
disp(b,"b=");
disp(a,"a=");
```
## OUTPUT (LPF) : 
<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/62b17a17-7e0a-4eef-bba8-73b7fb0e8265" />

## OUTPUT (HPF) : 
<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/85b42ca5-2971-410f-91ea-8baf85c8eef3" />

## RESULT: 
A third order Chebyshev Type I high-pass filter was designed with cutoff frequency 1500 Hz and sampling frequency 5000 Hz. The frequency response shows ripple in the passband and sharp attenuation in the stopband.
