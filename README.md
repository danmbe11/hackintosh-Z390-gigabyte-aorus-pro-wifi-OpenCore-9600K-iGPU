# **Big Sur hackintosh - Z390 Gigabyte Aorus Pro Wifi - 9600K - UHD630**
![Screenshot](screenshot.png)

## **Information**
Hackintosh EFI files for Z390 Aorus Pro Wifi. Other devs with this exact motherboard state that it will 'never be possible' to make the integrated WiFi & Blueooth work - well, they're wrong, it works perfectly fine using using itlwm from @zxystd
Feel free to download & use this as a helping point for your very own hackintosh build, but keep in mind:
  - You will need to start with macOS Catalina first (I went for 10.15.7), then upgrade from there. Make backups throughout the whole process!
  - If you aren't using iGPU, make all the neccessary changes for your dGPU
  - Remove the GPU_DISABLE SSDT (and inside config.plist) if you do not have a dedicated card that needs disabling in your system
  - Change the MLB, ROM, SystemSerialNumber and SerialUUID inside of config.plist
  - Make an OC snapshot if you are using different Kexts
  - You might want to add verbose for troubleshooting, at least until you get it to work as needed (`-v debug=0x100 keepsyms=1` into boot-args)

### **Specs**
  - **OpenCore:** 0.6.3
  - **macOS:** Big Sur 11.0.1
  - **Motherboard:** Gigabyte Z390 Aorus Pro Wifi (A305)
  - **CPU:** i5 9600K @ 5GHz
  - **GPU:** UHD630 (*RTX2060 Disabled & not used, using SSDT-GPU-DISABLE*)
  - **RAM:** Corsair Vengance Pro RGB 32GB 3733MHz
  - **Audio Codec:** Realtek ALCS1220A
  - **Ethernet Card:** Intel i219V(7)
  - **Wifi/BT Card:** Onboard

### **Credit / Useful links**
  - [**Dortania Install Guide - Intel Coffee Lake**](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#starting-point)
  - [**zxystd's itlwm**](https://github.com/OpenIntelWireless/itlwm)
  - [**Framebuffer Patching Guide**](https://www.tonymacx86.com/threads/guide-general-framebuffer-patching-guide-hdmi-black-screen-problem.269149/)
  - Changing the USB map? See [Port limit patch](https://github.com/corpnewt/USBMap#port-limit-patch) and [Dortania / USBMap - Intel mapping](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html)
  - [**Heliport**](https://github.com/OpenIntelWireless/HeliPort) - GUI for onboard Intel WiFi
  - [**Hackintool**](https://github.com/headkaze/Hackintool) - Very useful for debugging and system info


## **Functionality**
### **Working**
  - [x] On-board WiFi & Bluetooth
  - [x] FileVault
  - [x] Hardware acceleration
  - [x] Sound - All inputs & outputs
  - [x] Shutdown & Restart
  - [x] USB map with correct speeds ~~(*see USBmap-explanation.md to see which ports I changed as some ports are disabled and some only run at USB3/2 since I do not need the other standard on those particular connections*)~~ (To be added)

Everything else seems to be working correctly, these are just the functions that are usually the most painful to make work.

### **Not working**
  - [ ] Sleep (works, but not reliably and causes graphical glitches)
