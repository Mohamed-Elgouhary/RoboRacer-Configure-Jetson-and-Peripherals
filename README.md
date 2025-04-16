# roboracer-1.-Configuring-the-NVIDIA-Jetson-NX

# 1. Configuring the NVIDIA Jetson NX

**Equipment Used:**

- Pit/Host laptop/computer running any Operating System  
- Fully built RoboRacer vehicle  
- microSD card (16GB minimum)  
- m.2 SSD (optional)  
- USB micro cable (must have both data and power wires)  
- microSD card reader/writer for Pit/Host PC  
- SD card image burning software (e.g., Balena Etcher)  
- Terminal emulation software (e.g., PuTTY, screen, miniterm.py, etc.)

**Approximate Time Investment:** 1–2 hours

**Tip**

JetPack 5.0 Developer Preview is released on Apr. 7, 2022, with support for AGX Xavier, Xavier NX, and AGX Orin. We highly recommend flashing your Xavier with JetPack 5.0 since L4T 34.1 uses Ubuntu 20.04.

**1. Flash Jetson NX with Software**
The setup of the Nvidia Jetson NX is easy and convenient. NVIDIA provides a detailed step-by-step guide for getting started with the NVIDIA Jetpack Software on the NVIDIA Jetson NX. You can either follow this documentation here or follow our step-by-step introduction below.

1. Go to the NVIDIA Developers Download Center at https://developer.nvidia.com/downloads and click Jetson.

![image](https://github.com/user-attachments/assets/7b1d6ab0-84f7-4d18-8fdd-35daf8fa76aa)
<p align="center"><strong>NVIDIA Developers Download Center</strong></p>

2. Under SD Card Image Method, click Jetson Xavier NX Developer Kit.

![image](https://github.com/user-attachments/assets/d7fa8523-47e9-44a1-9785-5637ba7431ea)
<p align="center"><strong>Jetson Xavier NX Developer Kit downloads.</strong></p>

3. The next page will require you to log in with an NVIDIA Developer Program login. If you do not have one, click Join Now - Registration is free. If you already have an account, click Login.

![image](https://github.com/user-attachments/assets/85b2db46-6ca4-4be6-8ce2-8fb507be7545)
<p align="center"><strong>NVIDIA Developer Program login page.</strong></p>

4. Once you have logged in, you will be redirected to your profile settings page. At the top of this page, you should see a banner with a button with the text “Jetson Xavier NX Developer Kit SD Card Image.” Click this button.

![image](https://github.com/user-attachments/assets/83f7a00b-3565-4ed4-858a-c0e103e76f00)
<p align="center"><strong>NVIDIA Developer Program profile page download button.</strong></p>

5. Once the zip file has finished downloading, extract it. This will create a new file, sd-blob.img. This is the file that contains the NVIDIA Jetson Xavier NX Developer Kit software and operating system.
6. Put the acquired microSD card into the SD card reader/writer and then plug the SD card reader into the Host PC.
7. Download, install, and launch SD card image burning software [Etcher](https://etcher.balena.io/).
