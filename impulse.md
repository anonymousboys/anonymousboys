%2020UEC2561 Rishabh Jain ECE-2
%Convolution with impulse.
close all
clear all
A=1000
t1= -10:0.001:10
y1=A*rectangularPulse(-0.001,0.001,t1)
subplot(3,1,1)
plot(t1,y1)
title ('Impulse pulse')
xlabel('time t')
ylabel('Amplitude')
t2= -10:0.001:10
y2=sin(2*pi*t2)
subplot(3,1,2)
plot(t2,y2)
title ('sine wave')
xlabel('time t')
ylabel('Amplitude')
t3= -20:0.001:20
c= conv(y2,y1)
subplot(3,1,3)
plot(t3,c)
title ('Convolution')
xlabel('time t');ylabel('Amplitude')

Convolution with impulse(Time shifted)
close all
clear all
A=1000
t1= -10:0.001:10
y1=A*rectangularPulse(2.00,2.001,t1)
subplot(3,1,1)
plot(t1,y1)
title ('Impulse pulse')
xlabel('time t')
ylabel('Amplitude')
t2= -10:0.001:10
y2=sin(2*pi*t2)
subplot(3,1,2)
plot(t2,y2)
title ('sine wave')
xlabel('time t')
ylabel('Amplitude')
t3= -20:0.001:20
c= conv(y2,y1)
subplot(3,1,3)
plot(t3,c)
title ('Convolution after shifting')
xlabel('time t');ylabel('Amplitude')
