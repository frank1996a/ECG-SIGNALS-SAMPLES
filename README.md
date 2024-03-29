% Cargar datos de señal ECG desde un archivo .mat
load('ecg_data.mat');  % Asegúrate de tener el nombre correcto del archivo

% Parámetros de muestreo
fs_original = 1000;  % Frecuencia de muestreo original en Hz
nueva_fs = 250;  % Nueva frecuencia de muestreo en Hz

% Muestrear la señal a la nueva frecuencia de muestreo
ecg_muestreada = resample(ecg_data, nueva_fs, fs_original);

% Graficar la señal original y la señal muestreada
t_original = (0:length(ecg_data)-1) / fs_original;
t_muestreo = (0:length(ecg_muestreada)-1) / nueva_fs;

figure;
subplot(2,1,1);
plot(t_original, ecg_data);
title('Señal ECG Original');
xlabel('Tiempo (s)');
ylabel('Amplitud');

subplot(2,1,2);
plot(t_muestreo, ecg_muestreada);
title('Señal ECG Muestreada');
xlabel('Tiempo (s)');
ylabel('Amplitud');

% Opcional: Guardar la señal muestreada en un archivo
% save('ecg_muestreada.mat', 'ecg_muestreada', 'nueva_fs');a
![image](https://github.com/frank1996a/ECG-SIGNALS-SAMPLES/assets/119448736/e20b772c-db04-4177-a386-3e1ee1f7fd50)
![image](https://github.com/frank1996a/ECG-SIGNALS-SAMPLES/assets/119448736/b4b540ca-bfe4-48c3-a61d-fb140e6140a5)
