# SSB-T1-C12-EVEN
AIM:

To write a program for SSB in SCILAB and verify the output.

EQUIPMENTS NEEDED:

.Computer with i3 Processor

.SCI LAB

ALGORITHM:

Define the Function: Specify the function you want to simulate. For example, f(x)=sin⁡(x)f(x)=sin(x) or any other function.
Generate Sample Points: Decide on the range and the number of sample points. Generate these sample points within the desired range.
Evaluate the Function: Compute the function values at each of these sample points.
Compute Mean, Variance and Cross Correlation: Use Scilab's functions to calculate the mean and variance of the computed function values.
Display Results: Output the computed mean variance and Cross Correlation
PROCEDURE:

1.Refer Algorithms and write code for the experiment.

2.Open SCILAB in System

3.Type your code in New Editor

4.Save the file

5.Execute the code If any Error, correct it in code and execute again

6.Verify the generated results

PROGRAM:

    clc;
    clear;
    close;
    
    // Step 1: Time vector
    t = 0:0.00001:0.01;
    
    // Given values
    Am = 16.9;
    Ac = 33.8;
    fm = 606;
    fc = 6060;
    
    // Step 2: Message signal
    m = Am * cos(2 * %pi * fm * t);
    
    // Step 3: Hilbert Transform
    mh = hilbert(m);   // analytic signal
    mh = imag(mh);     // Hilbert transform part
    
    // Step 4: Carrier signals
    cos_c = cos(2 * %pi * fc * t);
    sin_c = sin(2 * %pi * fc * t);
    
    // Step 5: SSB Signals
    USB = Ac * (m .* cos_c - mh .* sin_c);
    LSB = Ac * (m .* cos_c + mh .* sin_c);
    
    // -------- PLOTTING --------
    subplot(3,1,1);
    plot(t, m);
    title("Message Signal");
    
    subplot(3,1,2);
    plot(t, USB);
    title("SSB - Upper Sideband (USB)");
    
    subplot(3,1,3);
    plot(t, LSB);
    title("SSB - Lower Sideband (LSB)");
OUTPUT GRAPH:
<img width="940" height="559" alt="image" src="https://github.com/user-attachments/assets/09123974-bf65-4478-ac4a-160044a6c9b0" />

![20260406_173642](https://github.com/user-attachments/assets/88b21266-8e3e-48ab-b49e-fbfab03e1bbc)

RESULT:
![20260406_173656](https://github.com/user-attachments/assets/daaaa6b8-79c0-4158-be6c-48fadfb1a0da)

