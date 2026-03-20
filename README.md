# Design-of-FIR-Filters-using-hamming-window

# DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
clear;
close;

M = 51;              // Filter length
fc = 0.4;            // Normalized cutoff frequency (0 to 0.5)

// Create Hanning window
n = 0:M-1;
w = 0.5 - 0.5 * cos(2 * %pi * n / (M-1));

// Ideal impulse response for Low Pass Filter
hd = sin(2 * %pi * fc * (n - (M-1)/2)) ./ (n - (M-1)/2);
hd((M-1)/2 + 1) = 2 * %pi * fc;  // fix center value

// Apply window
h = hd .* w;

// Normalize filter coefficients
h = h / sum(h);

// Display coefficients
disp(h);

// Plot impulse response
subplot(2,1,1);
plot(h);
xlabel('Samples');
ylabel('Amplitude');
title('Impulse Response of Low Pass FIR Filter using Hanning Window');

// Frequency response
[H, f] = frmag(h, 512);
subplot(2,1,2);
plot(f, H);
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Frequency Response of Low Pass FIR Filter');
```

# OUTPUT
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/79e82e1d-91f2-4e07-b750-e787ed509950" />

# RESULT
Thus, a Low Pass FIR Digital Filter was successfully designed using the Hanning window method in SCILAB.
