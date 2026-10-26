# Channel Simulation: Gaussian Channel (Rayleigh Channel) Different Signal-to-Noise Ratios for 4-8-16QAM Modulation Bit Error Rate Simulation [Attached All MATLAB Code]

MATLABSimulation codeclc\nclose all\nclear\nSNR=0:1:20;                 %SNR Variation Range\nSNR1=0.5*(10.^(SNR/10));    % Convert the signal-to-noise ratio to Cartesian coordinates\nN=1000000;                  % Simulation points\nM1=4;                       %4QAM\nM2=8;                       %8QAM\nM3=16;                      %16QAM\nK=0.5;\nx1=randi([0,M1-1],1,N);         % Generate random signals\nx2=randi([0,M2-1],1,N);\nx3=randi([0,M3-1],1,N);\nR=raylrnd(0.5,1,N);         % Generate Rayleigh signal\nh1=qammod(x1,M1);            %4QAM modulation\nh2=qammod(x2,M2);            %8QAM modulation\nh3=qammod(x3,M3);            %16QAM modulation\nH1=h1.*R;                   %4QAM through Rayleigh channel\nH2=h2.*R;                   %8QAM through Rayleigh channel\nH3=h3.*R;                   %16QAM through Rayleigh channel\nfor i=1:length(SNR)\n    yAn1=awgn(h1,SNR(i),'measured'); \n    yA1=qamdemod(yAn1,M1);     \n    [bit_A1,~]=biterr(x1,yA1); \n    QAM4_AWGN(i)=bit_A1/N;\n    \n    yAn2=awgn(h2,SNR(i),'measured'); \n    yA2=qamdemod(yAn2,M2);     \n    [bit_A2,~]=biterr(x2,yA2); \n    QAM8_AWGN(i)=bit_A2/N;\n    \n    yAn3=awgn(h3,SNR(i),'measured'); \n    yA3=qamdemod(yAn3,M3);     \n    [bit_A3,~]=biterr(x3,yA3); \n    QAM16_AWGN(i)=bit_A3/N;\n    \n    yRn1=awgn(H1,SNR(i),'measured');\n    yR1=qamdemod(yRn1,M1);     \n    [bit_R1,~]=biterr(x1,yR1);\n    QAM4_Ray(i)=bit_R1/N; \n    \n    yRn2=awgn(H2,SNR(i),'measured');\n    yR2=qamdemod(yRn2,M2);     \n    [bit_R2,~]=biterr(x2,yR2);\n    QAM8_Ray(i)=bit_R2/N; \n    \n    yRn3=awgn(H3,SNR(i),'measured');\n    yR3=qamdemod(yRn3,M3);     \n    [bit_R3,~]=biterr(x3,yR3);\n    QAM16_Ray(i)=bit_R3/N; \n    \nend\n% QPSK_t_AWGN=1/2*erfc(sqrt(10.^(SNR/10)/2));   %AWGNUnder the channelQPSKTheoretical bit error rate\n% QPSK_t_Rayleigh = -(1/4)*((1-sqrt(SNR1./(SNR1+1))).^2 + (1-sqrt(SNR1./(SNR1+1))))\n​\n% Draw a graph\nfigure\nsemilogy(SNR,QAM4_AWGN,'r*');hold on;\nsemilogy(SNR,QAM8_AWGN,'yo');\nsemilogy(SNR,QAM16_AWGN,'c+');\nsemilogy(SNR,QAM4_Ray,':b*');\nsemilogy(SNR,QAM8_Ray,':go'); \nsemilogy(SNR,QAM16_Ray,'m+');\n​\ngrid on;\naxis([-1 20 10^-4 1]);\nlegend('4QAM-AWGNSimulation','8QAM-AWGNSimulation','16QAM-AWGNSimulation',...\n    '4QAM-RayleighSimulation','8QAM-RayleighSimulation','16QAM-RayleighSimulation');\ntitle('PSKError performance analysis');\nxlabel('Signal-to-noise ratio (dB)');ylabel('BER');\n​\nMATLABSimulation results  

## Images

![(Channel Simulation)4-8-16 QAM Modulation Bit Error Rate Simulation of Gaussian Channels (Rayleigh Channels) at Different Signal-to-Noise Ratios [Attached All MATLAB Code]](01.jpg)
![(Channel Simulation)4-8-16 QAM Modulation Bit Error Rate Simulation of Gaussian Channels (Rayleigh Channels) at Different Signal-to-Noise Ratios [Attached All MATLAB Code]](02.jpg)
![(Channel Simulation)4-8-16 QAM Modulation Bit Error Rate Simulation of Gaussian Channels (Rayleigh Channels) at Different Signal-to-Noise Ratios [Attached All MATLAB Code]](03.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
