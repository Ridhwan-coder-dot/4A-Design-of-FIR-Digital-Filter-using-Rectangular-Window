# FIR-FILTER-DESIGN
# EXP 4 A: Design-of-FIR-Digital-Filter-using-Rectangular-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Rectangular-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
lc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M - 1) / 2; // Center Value

for n = 1:M
    if (n == alpha + 1)
        hd(n) = Wc / %pi;
    else
        hd(n) = sin(Wc * ((n - 1) - alpha)) / (((n - 1) - alpha) * %pi);
    end
end

// Rectangular Window
for n = 1:M
    W(n) = 1;
end

// Windowing filter coefficients
h = hd .* W;

disp(h, 'Filter Coefficients are');

[hzm, fr] = frmag(h, 256);

// Magnitude Response
subplot(2, 1, 1);
plot(2 * fr, hzm);
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Rectangular Window');

// Magnitude Response in dB
hzm_dB = 20 * log10(hzm);

subplot(2, 1, 2);
plot(2 * fr, hzm_dB);
xlabel('Normalized Digital Frequency W');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Rectangular Window');

# CALCULATION :
<img width="899" height="1599" alt="WhatsApp Image 2026-09-15 at 08 52 27" src="https://github.com/user-attachments/assets/dab21777-9a95-45ad-8707-c599f5096f56" />
<img width="899" height="1599" alt="WhatsApp Image 2026-09-15 at 08 52 41" src="https://github.com/user-attachments/assets/13a436d7-0587-4f67-a5be-372ee608a3b0" />

# OUTPUT: 
<img width="645" height="798" alt="image" src="https://github.com/user-attachments/assets/f2f1b1bf-1b38-4de6-9ba5-4730d82c0c6e" />
<img width="932" height="872" alt="image" src="https://github.com/user-attachments/assets/c40fd966-0acd-4078-a76d-c6a10fbd061b" />


# RESULT: 

Thus design of low pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n)=1-Wc/ %pi ; 
else 
hd(n) =-sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 
end 
end 
// Rectangular Window 
for n = 1:M 
W(n) =1; 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR LPF using Rectangular Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR HPF using Rectangular Window');

# OUTPUT: 
<img width="990" height="890" alt="image" src="https://github.com/user-attachments/assets/7d6190a3-25f0-4fbc-a661-172d057b3292" />
<img width="632" height="797" alt="image" src="https://github.com/user-attachments/assets/1792a209-a3ce-4861-afff-95140c234ff4" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =(Wc2-Wc1)/%pi ; 
else 
hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Rectangular Window 
for n = 1:M 
W(n) =1; 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Rectangular Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Rectangular Window');

# OUTPUT: 
<img width="945" height="858" alt="image" src="https://github.com/user-attachments/assets/bbf5bf8e-be81-4907-8be9-931ee35d9f0b" />
<img width="622" height="805" alt="image" src="https://github.com/user-attachments/assets/cccffa75-e35c-49fe-a391-726d5211a784" />



# RESULT: 
Thus design of BAND pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc=input('Enter the Digital Cut off frequency ='); 
Wc2=Wc(2); 
Wc1=Wc(1); 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
if (n ==alpha+1) 
hd(n) =1-((Wc2-Wc1)/%pi) ; 
else 
hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
end 
end 
// Rectangular Window 
for n = 1:M 
W(n) =1; 
end 
//Windowing filter coefficients 
h = hd.*W; 
disp(h,'Filter Coefficients are') 
[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of  FIR BSF using Rectangular Window ') 
hzm_dB = 20* log10 (hzm); 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Rectangular Window');

# OUTPUT: 
<img width="670" height="800" alt="image" src="https://github.com/user-attachments/assets/4c8f7a55-fb66-49f5-b980-a1b05e7c40d0" />
<img width="940" height="847" alt="image" src="https://github.com/user-attachments/assets/2543017b-210a-45a1-b765-4bc10c094a64" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.
