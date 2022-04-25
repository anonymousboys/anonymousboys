clc;
close all;
clear;
N=1000;
samp = (rand(1,N)-0.5)*(sqrt(12));
for n=1:1:5
 L=2^n;
 delta = (max(samp)-min(samp))/L;
 X_bit_axis(n) = n;
 for nn=1:1:N
 for kk=1:1:L
 Q_lev = min(samp)-delta/2 + (kk)*delta;
 if samp(nn) >= Q_lev - delta/2 &&
samp(nn)<Q_lev+delta/2
 sampQ(nn) = Q_lev;
 else
 end
 end
 end
 Q_error = samp-sampQ;
 Q_Noise(n)=mean(Q_error.*Q_error);
end
plot(X_bit_axis,Q_Noise,'-.b');
hold on;
Ng=100;
sampg = randn(1,Ng);
for ng=1:1:5
 Lg=2^ng;
 deltag = (max(sampg)-min(sampg))/Lg;
 X_bit_axisg(ng)=ng;
 for nng=1:1:Ng
 for kkg=1:1:Lg
 Q_levg = min(sampg)-deltag/2 + (kkg)*deltag;
 if sampg(nng)>= Q_levg-deltag/2 && sampg(nng) <
Q_levg+deltag/2;
 sampQg(nng) = Q_levg;
 else
 end
 end
 end
 Q_errorg = sampg - sampQg;
 Q_Noiseg(ng)=mean(Q_errorg.*Q_errorg);
end
plot(X_bit_axisg,Q_Noiseg,'-.r');
