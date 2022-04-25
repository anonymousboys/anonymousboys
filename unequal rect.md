Unequal width rectangular pulses convolution
t= -7:0.01:7;
t1= -0.5;
t2= 0.5;
t3= -1;
t4=1;
u1=(t>=t1);
u2=(t>=t2);
u3=(t>=t3);
u4=(t>=t4);
A= 3;
rect1= A*(u1-u2);
rect2= A*(u3-u4);
w= conv(rect1,rect2);
subplot(3,1,1);plot(t,rect1);title('Recatangular Pulse',
'FontSize', 7);
ylabel('magnitude');
xlabel('t');
subplot(3,1,2);plot(t,rect2);title('Recatangular Pulse',
'FontSize', 7);
ylabel('magnitude');
xlabel('t');
t1= -14:0.01:14;
subplot(3,1,3);plot(t1,w);title('Convolution', 'FontSize', 7);
ylabel('magnitude');
xlabel('t');
