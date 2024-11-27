# lab-5-
clc;
close all;
EbN0dB = 0:1:20;
EbN0 = 10.^(EbN0dB / 10);
PE_BPSK = 0.5 * erfc(sqrt(EbN0));
PE_BfSK = 0.5 * erfc(sqrt(EbN0 / 2));
PE_BaSK = 0.5 * erfc(sqrt(EbN0 / 4));
semilogy(EbN0dB, PE_BPSK, 'r', 'LineWidth', 2);
hold on;
semilogy(EbN0dB, PE_BfSK, 'b', 'LineWidth', 2);
semilogy(EbN0dB, PE_BaSK, 'k', 'LineWidth', 2);
xlabel('Eb/N0 (dB)');

ylabel('BER');
title('Bit Error Rate (BER) vs Eb/N0 for Different Modulation Schemes');
grid on;
legend('BPSK', 'BFSK', 'BaSK');
