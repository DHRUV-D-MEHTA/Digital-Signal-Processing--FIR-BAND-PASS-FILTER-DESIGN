# Digital-Signal-Processing--FIR-BAND-PASS-FILTER-DESIGN
## AIM:
To generate design of Band Pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Band Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM: 

clc; % clear screen 

clear all; % clear screen 

close all; % close all figure windows 

Wc1=input('enter the value of Wc1=');  

Wc2=input('enter the value of Wc2=');  

N=input('enter the value of N='); 

alpha=(N-1)/2;  

eps=0.001;  

% Band Pass Filter Coefficient 

n=0:1:N-1;  

hd=(sin(Wc2*(n-alpha+eps)) - sin(Wc1*(n-alpha+eps)))./((n-alpha+eps)*pi);

% Blackman Window Sequence  

n=0:1:N-1;  

wh=0.42 - 0.5*cos((2*pi*n)/(N-1)) + 0.08*cos((4*pi*n)/(N-1));

hn=hd.*wh;  

% Plot the Band Pass Filter with Blackman window Technique 

w=0:0.01:pi;  

h=freqz(hn,1,w); 

plot(w/pi,abs(h),'blue');

xlabel('Normalized Frequency');

ylabel('Magnitude');

title('Band Pass FIR Filter using Blackman Window');


## OUTPUT:
<img width="1918" height="1017" alt="Screenshot 2026-03-26 114801" src="https://github.com/user-attachments/assets/be35719e-f051-48fb-a4a3-20c86c3f8a94" />

## RESULT:
![WhatsApp Image 2026-04-01 at 6 06 03 PM](https://github.com/user-attachments/assets/a2c832fc-3d2f-4b69-a48d-053f23b93572)
