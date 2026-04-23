# OCN

Experiment 3 – Signal Attenuation (SCILAB)

clear;
clc;
close;

Pi = 120;
Po = 3;
L = 8;

Alpha_dB_L = 10 * log10(Pi/Po);
Alpha_dB = Alpha_dB_L / L;
A = Alpha_dB * 10 + 9;
Pi_by_Po = 10^(round(A)/10);

disp('(a) Overall signal attenuation is');
disp(Alpha_dB_L);

disp('(b) Signal attenuation per kilometer is (dB/km):');
disp(Alpha_dB);

disp('(c) Overall signal attenuation for 10 km optical link with splices is (dB):');
disp(A);

disp('(d) Numerical Input/Output power ratio is:');
disp(Pi_by_Po);



Experiment 6 – Material Dispersion (SCILAB)

// Example 3.6
// Program to estimate Material Dispersion Parameter
// and RMS Pulse Broadening per kilometer

clear;
clc;
close;

// Given data
lambda = 0.85 * 10^(-6);        // metre - WAVELENGTH
L = 1;                           // km - DISTANCE
MD = 0.025;                      // MATERIAL DISPERSION = mod(lambda^2 * (d^2n1/dlambda^2))
c = 2.998 * 10^8;               // m/s - VELOCITY OF LIGHT IN VACUUM
sigma_lambda = 20 * 10^(-9);    // metre - RMS SPECTRAL WIDTH

// Material Dispersion Parameter
M = MD / (lambda * c);

// RMS Pulse Broadening per kilometer
sigma_m = sigma_lambda * L * M;

// Displaying the Results in Command Window
printf("\n\n\t Material Dispersion Parameter is %0.1f ps/nm/km \n", M * 10^6);
printf("\n\n\t R.M.S. pulse broadening per kilometer is %0.2f ns/km.\n", sigma_m / 10^(-12));



Experiment 7 – Link Budget (MATLAB)

% To find power budget
N = [5 10 50];

alpha = input('Enter attenuation in dB per km: ');
ltp = input('Enter coupling loss in dB: ');
lth = input('Enter coupling throughput in dB: ');
li = input('Enter intrinsic coupling loss in dB: ');
lc = input('Enter coupler to fiber loss in dB: ');
l = input('Enter link length in km: ');

Fl = alpha * l;   % fiber loss in dB

pbudget = N * [(alpha*l + 2*lc + li + lth) - alpha*l - 2*lth + 2*ltp];

disp('N =');
disp(N);
disp('Fl =');
disp(Fl);
disp('pbudget =');
disp(pbudget);
