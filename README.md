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

![image](https://github.com/user-attachments/assets/59c4df0e-bdac-4edc-ba89-09766c235934)
<p align="center"><strong>SD card burner software Etcher.</strong></p>

8. Choose Flash the file and select the image you downloaded from NVIDIA. When the file selection window comes up, choose the sd-XXXX.img file extracted earlier.

![image](https://github.com/user-attachments/assets/fd0d230b-f4dd-49b0-af84-4a9560487e7e)
<p align="center"><strong>File selection window.</strong></p>

9. For the “target” device, choose the microSD card in the microSD card reader/writer.

![image](https://github.com/user-attachments/assets/0187970b-9f75-4848-8249-16798c552291)
<p align="center">Target selection window.</strong></p>

10. Click “Flash!” (or similar for your software). This process will take some time and is mainly depending on the speed write speed of your microSD card (20+ minutes).

![image](https://github.com/user-attachments/assets/5f4772fe-c903-4047-a68d-ec37f3fec4c0)
<p align="center">Flashing process.</strong></p>

11. Once the flashing process is complete, verify that any activity lights on your SD card reader/writer are no longer blinking. Properly un-mount/eject the microSD card before physically removing it from the reader/writer.
12. Now its time to bring the software on the NVIDIA Jetson NX. Insert the flashed microSD card into the NVIDIA Jetson Xavier NX module with the label facing up. Push the microSD card all the way in until it locks into place with a small click. The edge of the microSD card should be flush with the PCB of the NVIDIA Jetson Xavier NX module and carrier board.

![image](https://github.com/user-attachments/assets/0328444e-1031-4b8a-ba06-4b7784413ebd)
<p align="center"><strong>Insert SD card.</strong></p>

![image](https://github.com/user-attachments/assets/f622b614-1c45-472e-b0eb-da48a0c3671f)
<p align="center">SD card flush.</strong></p>

13. When you have entered the microSD card you can power up the Jetson NX on the RoboRacer car for the first time. First of all plug the following into the Jetson NX:
    - USB Port: A keyboard
    - USB Port: A mouse
    - HDMI Port: An external monitor

14. Now you can provide energy for the RoboRacer car. You either do this with the battery on the car or plug in an external power supply that provides 16V. The Jetson Xavier NX Developer Kit will power on and boot automatically after you provided the power supply.

**Important**

The barrel jack on the powerboard is only rated for 9.0V - 16.0V. The power supplies that come with the Jetson NX are 19V and therefore have a higher voltage. Do not plug those in. Otherwise you will destroy your powerboard.

15. A green LED next to the Micro-USB connector will light as soon as the developer kit powers on. When you boot the first time, the Jetson Xavier NX Developer Kit will take you through some initial setup, including:

  - Review and accept NVIDIA Jetson software EULA
  - Select system language, keyboard layout, and time zone
  - Connect to Wireless network
  - Create username, password, and computer name
  - Log in

16. After logging in you should see the following screen. Congratulations, your NVIDIA Jetson NX on your RoboRacer car is ready to go.

![image](https://github.com/user-attachments/assets/1c618b97-bd03-4836-a739-6a5e77131e68)
<p align="center"><strong>First boot of the NVIDIA Jetson NX.</strong></p>

# 2. Run Jetson NX from SSD

In the build instruction we applied an SSD NVMe on to the Jetson NX. We will now make use of this SSD by switching the rootfs to point to the SSD. In effect, the system will now run from the SSD, the SD card is only there to boot the system. Therefore everything you install on your system will automatically installed on the SSD.

**1. Format SSD**

![Screenshot from 2025-04-16 19-12-14](https://github.com/user-attachments/assets/1aa9f00e-bb26-4acd-b2d1-b583e54588d5)
<p align="center"><strong>Open Disks</strong></p>

![Screenshot from 2025-04-16 19-14-08](https://github.com/user-attachments/assets/5ebf8dd6-c847-42f2-bbb3-692d9701d729)
<p align="center"><strong>Choose Format Disk ...</strong></p>

![Screenshot from 2025-04-16 19-15-27](https://github.com/user-attachments/assets/de8051c9-0a9c-4f6d-8683-f5d8362a9fb7)
<p align="center"><strong>Click Format...</strong></p>

![Screenshot from 2025-04-16 19-17-09](https://github.com/user-attachments/assets/a7caf2ea-6e36-45c9-9a83-c0f7afaa3de0)
<p align="center"><strong>Click Format</strong></p>

![Screenshot from 2025-04-16 19-18-22](https://github.com/user-attachments/assets/55f1959d-4f20-4ef8-a956-d40dbf4ff7bb)
<p align="center"><strong>Click + button to add partition</strong></p>

![Screenshot from 2025-04-16 19-19-42](https://github.com/user-attachments/assets/7ec55e7d-0087-44e9-a6c6-eab8cdd9aa3d)
<p align="center"><strong>Make 16 GB Free Space</strong></p>

![Screenshot from 2025-04-16 19-22-48](https://github.com/user-attachments/assets/b922633a-92f0-4ce5-a2d6-1fb450f59a5a)
<p align="center"><strong>Set the volume name and set its type to Ext4</strong></p>

![Screenshot from 2025-04-16 19-24-46](https://github.com/user-attachments/assets/f542dbcf-ab33-4b3d-b14f-77a72898650a)
<p align="center"><strong>Notice that the device is /dev/nvme0n1p1</strong></p>

**2. Disk Setup**

On the JetsonHacks account on Github, there is a repository rootOnNVMe. Clone the repository:

```bash
git clone https://github.com/jetsonhacks/rootOnNVMe
```

and switch over to that repository’s directory:
```bash
cd rootOnNVMe
```

Next, copy the rootfs of the eMMC/SD card to the SSD
```bash
./copy-rootfs-ssd.sh
```

Finally, we will add a service which will run a script when the system starts up. The script will “pivot the root” to the SSD so that the system will run from the SSD.
```bash
./setup-service.sh
```

After setting up the service, reboot for the changes to take effect.
```bash
sudo reboot
```
# 3. Updating Packages

All further steps assume that your NVIDIA Jetson Xavier NX Developer Kit is connected to the internet. You can execute all the commands directly in the terminal application of the NVIDIA Jetson. Now we are updating the Ubuntu system on the Jetson NX.

1. To update the list of available packages, run
```bash
sudo apt update
```

2. To install all available updates, run
```bash
sudo apt full-upgrade
```

3. Once all packages have been upgraded, run 
```bash
sudo reboot
```
to restart the Developer Kit and apply any changes.

# 4. Creating a Swapfile

Run the following commands to create a swapfile which can help with memory-intensive tasks

```bash
sudo fallocate -l 4G /var/swapfile
sudo chmod 600 /var/swapfile
sudo mkswap /var/swapfile
sudo swapon /var/swapfile
sudo bash -c 'echo "/var/swapfile swap swap defaults 0 0" >> /etc/fstab'
```

