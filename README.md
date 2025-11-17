# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:

![WhatsApp Image 2025-11-16 at 19 34 41_3757edac](https://github.com/user-attachments/assets/1645516f-56ea-454d-b7d3-07b019d08bf0)

![WhatsApp Image 2025-11-16 at 19 34 41_1e39435d](https://github.com/user-attachments/assets/a12c9d7a-e2ae-4d84-82d5-79885a7f030c)

![WhatsApp Image 2025-11-16 at 19 34 41_8ed6933a](https://github.com/user-attachments/assets/61585256-2bc9-4959-86a0-436eebd43024)

![WhatsApp Image 2025-11-16 at 19 34 42_c29c6290](https://github.com/user-attachments/assets/864eaf73-2f52-4445-ae71-1f37ac24da34)

![WhatsApp Image 2025-11-16 at 19 38 46_9473479b](https://github.com/user-attachments/assets/5e6fc8ef-0ba0-412d-9d47-2ac32cf47714)

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 
```
num=[1]
den=[conv(1,0),conv(1,0.5),conv(1,0.2)]
sys=tf(num,den)
w=logspace(-1,2,1000)
[mag phase]=bode(sys,w)
mag=squeeze(mag)
phase=squeeze(phase)
theta=deg2rad(phase)
polarplot(theta,mag,'LineWidth',1.5)
[gm pm wpc wgc]=margin(sys)
if (wpc>wgc)
    disp('stable')
elseif (wpc==wgc)
    disp('marginally stable')
else
    disp('unstable')
end
```

## Output:

<img width="1055" height="975" alt="image" src="https://github.com/user-attachments/assets/bd1578ec-3fae-4474-8462-abf0c6d23f8e" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 3.57 dB <br>
Phase Margin = 27.9 degrees <br>
Gain crossover frequency = 1.76 rad/sec <br>
Phase crossover frequency = 4.47 rad/sec <br>
The system is stable.
