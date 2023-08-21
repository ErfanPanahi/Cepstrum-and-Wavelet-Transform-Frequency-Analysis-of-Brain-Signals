# Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals
In this repository, we delve into the exploration of Wavelet Transform and Short-Time Fourier Transform. We then examine several examples of Fourier analysis applications, including Dual Tone Multi-Frequency and image compression. Finally, we investigate the frequency domain of the EEG signal and discuss the Cepstrum transformation.

The completed sections of the project are as follows: (CA2_Matlab_810198369.mlx)

**1- Short-Time Fourier Transform and Wavelet Transform**

As you know, the Fourier transform operates by convolving a signal with a series of sinusoidal signals of different frequencies. In fact, through this method, we can determine which frequencies exist in the processed signal. If the dot product between the points of interest in the target signal and a sinusoidal signal with a specific frequency results in a large value, then it can be concluded that there is significant overlap between these two signals, and consequently, that specific frequency will be observed in the frequency spectrum of the target signal. One important aspect of the Fourier transform is its high frequency resolution in the frequency domain, while having zero resolution in the time domain. In other words, the Fourier transform has the capability to precisely tell us what frequencies are present in a signal, but it cannot determine when the desired frequency occurs within the signal.

To overcome this limitation, the Short-Time Fourier Transform (STFT) method is used. In this approach, the original signal is divided into several segments of equal length. These segments (windows) may overlap or be non-overlapping. The main idea of this transform is that if, for instance, we divide the signal into 10 segments and the Fourier transform identifies a specific frequency in the second segment, then with high certainty, we can say that this frequency occurs within the range of 0.2 to 0.3 of the original signal.

In this section, we became familiar with the Short-Time Fourier Transform (STFT). The main drawback of the STFT is that as we decrease the size of the windows, we will be able to more accurately determine at what time a frequency occurred in the original signal. However, on the other hand, we will obtain less information about the frequency magnitude of the original signal. Similarly, as we choose larger window sizes, we will gather more information about the frequency magnitude and less information about the time of occurrence of the frequency.

A better method for analyzing a signal with a dynamic frequency spectrum is to use the Wavelet Transform. In this transform, the original signal can be multiplied by wavelets at different moments in time. In the first step, we start with the initial points of the signal and gradually move the wavelet towards the end of the signal. This operation is called convolution. After performing convolution with the original wavelet signal, we can scale it in a way that it becomes larger and repeat the process. Therefore, the Wavelet Transform provides us with information about both the two dimensions of time and scale (or frequency) for a one-dimensional signal.

As can be seen in the images below, as the window size increases, the temporal resolution diminishes, resulting in less information about the timing and occurrence of the frequency. However, with the enlargement of the window size, we will obtain more information about the frequency value and frequency resolution.

![image](https://github.com/ErfanPanahi/Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals/assets/107314081/4e86b415-795a-4c64-b08d-938baf7c96ac)

![image](https://github.com/ErfanPanahi/Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals/assets/107314081/ccdf0803-3f3b-406b-a246-2140445cedf4)

**2- Detection of DTMF (Dual Tone Multi-Frequency) Sounds**

DTMF tones are dual-tone signals (two-tone signals with different frequencies) that are generated when dialing phone numbers and are sent to the central telecommunications center. Since human voice cannot produce these tones, one of the tones is created through a high-frequency group of tones, and the other tone is generated from a low-frequency group of tones. The reason for combining two frequencies together is to ensure that the generated frequency is not easily producible by human voice, preventing interference during information transmission.

DTMF tones are generally composed of 16 types of frequencies, representing numbers, telecommunication symbols (* and #), as well as letters A-D. For instance, the key 1 produces a low frequency of 697 Hz and a high frequency of 1209 Hz.

The primary application of DTMF tones is in telecommunications, where they are recognized as a signaling system. They use the voice frequency band over telephone lines to establish communication between telephone equipment and other switching centers. However, these codes can also be used to establish communication between electronic circuits and devices such as computers, mobile phones, and the like. Designers determine how to generate these codes based on the type of transmitter and receiver, either through hardware means (using ICs) or through software tools like MATLAB.

![image](https://github.com/ErfanPanahi/Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals/assets/107314081/ecfd1161-a0d4-4c4d-a643-53699bd742e8)


**3- Image compression using two-dimensional Fourier transform**

Changes in the elements of an image matrix are manifested by altering the intensity of light and color in the picture, and are recognized as the edges of the image. Therefore, rapid variations in the elements occur at the edges of the image, and it is expected that these rapid changes represent high frequencies, while conversely, gradual changes represent low frequencies in the image domain. This fact becomes evident through the two-dimensional Fourier transform of simple black and white images.

A very basic and simple method in reducing the size of an image, or in other words, image compression, is to disregard the preservation of partial values (which are related to image details) in this transformation, fft2. Instead, by replacing them with zeros in the transformation matrix, the image size is reduced.

To reduce the size of images, after obtaining the Fourier transform of the image matrix, we need to remove values whose transformed magnitudes are less than a specified threshold. The larger this threshold is, the less the reduction in image size. Then, the obtained transformed data undergoes a two-dimensional inverse Fourier transform, and finally, we observe the size of the output file.

![image](https://github.com/ErfanPanahi/Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals/assets/107314081/1e02b514-b145-4a22-9099-9c2e5d01670f)


![image](https://github.com/ErfanPanahi/Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals/assets/107314081/3d06f9c5-29ae-4e8c-8e66-68f961e9232a)


**4- Frequency analysis of brain signals**

The brainwave, electroencephalography (EEG) for short, records the electrical activity of the brain through the placement of surface electrodes on the scalp. In EEG, the electrical effects of neuronal activity in the brain are recorded and displayed as temporal signals. The figure below illustrates the different types of brain signals along with their frequencies.

![image](https://github.com/ErfanPanahi/Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals/assets/107314081/671cb9b2-652c-415a-886a-42e38eecf6a2)

**5- Introduction to Cepstrum transformation**

The Cepstrum transform is the result of applying the inverse Fourier transform on the logarithm of the Fourier transform. In fact, during the process of taking the Fourier transform, before returning to the time domain, in the same frequency domain, the logarithm of the signal's magnitude is obtained. This operation has several advantages, including the ability to sum two convolved signals in the frequency domain before taking the inverse Fourier transform, based on the properties of the logarithm. This approach finds numerous applications in signal processing, particularly in audio processing. It's worth mentioning that the independent variable, after the Capström transform, is referred to as "quefrency", and its unit is similar to time, namely seconds, although its interpretation is quite different from the conventional concept of time. For more information about this transform, you can refer to Chapter 13 of Oppenheim's book.

Furthermore, the first part of the term "cepstrum", namely "ceps", is essentially the reversed version of "spec", thus creating a semantic connection between the names "cepstrum" and "spectrum".

![image](https://github.com/ErfanPanahi/Cepstrum-and-Wavelet-Transform-Frequency-Analysis-of-Brain-Signals/assets/107314081/1bc0c28e-fdc1-4a89-9667-f8915fa51abb)

