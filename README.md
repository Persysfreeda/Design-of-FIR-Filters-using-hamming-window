# Design-of-FIR-Filters-using-hamming-window

# DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
clc;
clear;
close;

// --- Filter Specifications ---
M = 51;              // Filter length
fc = 0.4;            // Normalized cutoff frequency (0 to 0.5)

// --- Create Hamming Window ---
n = 0:M-1;
w = 0.54 - 0.46 * cos(2 * %pi * n / (M-1));

// --- Ideal Impulse Response (Low Pass FIR) ---
hd = sin(2 * %pi * fc * (n - (M-1)/2)) ./ (n - (M-1)/2);

// Fix division by zero at center
hd((M-1)/2 + 1) = 2 * %pi * fc;

// --- Apply Window ---
h = hd .* w;

// --- Normalize Coefficients ---
h = h / sum(h);

// --- Display Coefficients ---
disp("Filter Coefficients:");
disp(h);

// --- Plot Impulse Response ---
subplot(2,1,1);
plot(h);
xlabel('Samples');
ylabel('Amplitude');
title('Impulse Response of Low Pass FIR Filter using Hamming Window');

// --- Frequency Response ---
[H, f] = frmag(h, 512);

subplot(2,1,2);
plot(f, H);
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Frequency Response of Low Pass FIR Filter (Hamming)');


```

# OUTPUT
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/4e26ad68-9dc5-4b22-b888-9479c68957fb" />
<img width="1916" height="1198" alt="image" src="https://github.com/user-attachments/assets/aa6e6d70-1c07-453c-b8a3-7f1b6ab95d5e" />



# RESULT
Thus, a Low Pass FIR Digital Filter was successfully designed using the Hamming window method in SCILAB.
