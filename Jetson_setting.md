# Jetson Setting Manual
Last Updated : 2024.08.05

----
## step 0: Install sdkmanager to desktop
- download sdkmanager: https://developer.nvidia.com/sdk-manager
```
sudo apt update
sudo apt install libnss3-tools libcanberra-gtk-module
sudo apt install ./sdkmanager_2.1.0-11698_amd64.deb
sudo apt --fix-broken install # if error occured
```
- run `sdkmanager`


- enable ssh of desktop
```
sudo apt-get update
sudo apt-get install openssh-server
sudo systemctl start ssh
sudo systemctl enable ssh
```

----
## step 1: Install CTI-L4T & BSP
Follow: https://connecttech.com/resource-center/kdb373/
- desktop 20.04, jetpack 5.1.3
- Target Components -> only Jetson Linux.
- Pop up (SDK Manager is about to flash..., sdk manager is about to install sdk components... ) -> skip
- Install finish

#### BSP (Board Support Package)
- download link: https://connecttech.com/resource-center/l4t-board-support-packages/
- select right version and download .tgz 
- move .tgz to folder `~/nvidia/nvidia_sdk/JetPack_5.1.3_Linux_JETSON_AGX_ORIN_TARGETS/Linux_for_Tegra`

```
# Linux_for_Tegra directory
tar -xzvf CTI-L4T-ORIN-AGX-35.5.0-V002.tgz
cd CTI-L4T
sudo ./install.sh
cd .. # return to the Linux_for_Tegra directory
```

- After `sudo ./install.sh`, you can see
```
Success!
/home/nkm/nvidia/nvidia_sdk/JetPack_5.1.3_Linux_JETSON_AGX_ORIN_TARGETS/Linux_for_Tegra/CTI-L4T
CTI-L4T-ORIN-AGX-35.5.0-V002 Installed!
```
- and if you run `lsusb` in folder `Linux_for_Tegra`, you can see  
```
...
Bus 001 Device 016: ID 0955:7223 NVIDIA Corp. APX
...

```
- run `sudo ./cti-flash.sh` select `rogue-orin` - `base` - `a`
- takes very long time. If done, you can see
```
*** The target t186ref has been flashed successfully. ***
Reset the board to boot from internal eMMC.
```


Next, see the jetson screen. Install the SW (Similar to Ubuntu install)
- install chromium browser
- install, reset, and connect internet
- remember username and password!

----
## step 2: Jetpack SDK Components
Follow : https://connecttech.com/resource-center/kdb374/
- Target Components: except Jetson OS
- Pop-up -> enter the username/password created in jetson
- It takes a very long time to install
- 
You must see INSTALLATION COMPLETED SUCCESSFULLY

----
