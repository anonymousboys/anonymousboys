clc;
clear ;
close all;
Fs = 60;
t = -2.5:1/Fs:2.5;
x=1/ (sqrt (2*pi*0.01))*(exp(-t.^2/(2*0.01)));
y=5/ (sqrt (2*pi*0.01))*(exp(-t.^2/(2*0.01)));
x1=1/ (sqrt (2*pi*0.01))*(exp(-(t-1).^2/(2*0.01)));
y1=5/ (sqrt (2*pi*0.01))*(exp(-(t-1).^2/(2*0.01)));
w= conv(x,y);
w2= conv(x1,y);
w3= conv(x,y1);
subplot(7,1,1);plot(t,x);
title('Gaussian Function 1', 'FontSize', 7);
subplot(7,1,2);plot(t,y);
title('Gaussian Function 2', 'FontSize', 7);
subplot(7,1,3);plot(t,x1);
title('Gaussian Function 1 shifted by 1', 'FontSize', 7);
subplot(7,1,4);plot(t,y1);
title('Gaussian Function 2 shifted by 1', 'FontSize', 7);
t1=-5:1/Fs:5;
subplot(7,1,5);plot(t1,w);
title('Convolution of function 1 and 2 ', 'FontSize', 7);
subplot(7,1,6);plot(t1,w2);
title('Convolution of function 1(shifted) and 2 ', 'FontSize',
7);
subplot(7,1,7);plot(t1,w3);
title('Convolution of function 1 and 2(shifted) ', 'FontSize',
7);
