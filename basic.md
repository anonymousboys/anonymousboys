%2020UEC2561 Rishabh Jain ECE-2
%Convolution of 2 guassian pulses.
clc;
clear ;
close all;
Fs = 60;
t = -.5:1/Fs:.5;
x=1/ (sqrt (2*pi*0.01))*(exp(-t.^2/(2*0.01)));
y=1/ (sqrt (2*pi*0.01))*(exp(-t.^2/(2*0.01)));
w= conv(x,y);
subplot(3,1,1);plot(t,x);title('Gauss Pulse', 'FontSize', 7);
ylabel('magnitude');
xlabel('t');
subplot(3,1,2);plot(t,y);title('Gauss Pulse', 'FontSize', 7);
ylabel('magnitude');
xlabel('t');
t1=-1:1/Fs:1;
subplot(3,1,3);plot(t1,w);title('Convolution', 'FontSize', 7);
ylabel('magnitude');
xlabel('t');

%Plotting sin^2 , cos^2 , polynomial.
x=0:0.01:2*pi;
si=sin(x).^2;
co=cos(x).^2;
plot(x,si,x,co);
title('Sin^2(x) and Cos^2(x)','FontSize', 7);
ylabel('magnitude');
xlabel('t');

clc;
clear all;
close all;
t = (0:0.05:3);
e= 2*(t.^2) + 3*t + 9;
plot(t,e);
xlabel('time');
ylabel('amplitude');

%Plotting triangular wave.
clc;
clear;
close all;
T=1;
dt=0.002;
N=5;
t2=-1:dt:T-dt
a= triangularPulse(0,1/2,t2);
b= -triangularPulse(1/2,1,t2);
y=a+b;
plot(t2,y);
time_y=[];
y_periodic=[];
for i=-N:N-1,
 time_y=[time_y i*T+t2];
 y_periodic=[y_periodic y];
end
plot(time_y, y_periodic);
title('Triangular Wave');
xlabel('Time t');
ylabel('Amplitude');
axis([-5,5,-1.5,1.5]);

Rectangular pulse using array
t1=-2:0.01:-1; %time axis
t2=-1:0.01:1; %time axis
t3=1:0.01:2; %time axis
t=[t1 t2 t3];
x=[zeros(size(t1)) ones(size(t2)) zeros(size(t3))];
plot(t,x);title('Recatangular Pulse', 'FontSize', 7);
ylabel('magnitude');
xlabel('t');

%Plotting sin cos and sinc functions using subplot.
clc;
clear all;
close all;
t = (0:0.05:3); % time upper limit taken such that graph is till
6pi
x= sin(2*pi*t);
a= cos(2*pi*t);
b= sinc(2*pi*t);
subplot(3,1,1),plot(t,x);
ylabel('magnitude');
xlabel('t');
subplot(3,1,2),plot(t,a);
ylabel('magnitude');
xlabel('t');
subplot(3,1,3),plot(t,b);
ylabel('magnitude');
xlabel('t');
