<img src="https://github.com/user-attachments/assets/32f6e00b-b053-4be4-8618-bfb740c38932" width="350" title="oneplus8t"/>

**Last builds:** https://download.lineageos.org/devices/kebab/builds

### Unlocking the bootloader

Enable OEM unlock in the Developer options under device Settings, if present.
Connect the device to your PC via USB.
```
adb -d reboot bootloader
fastboot devices
fastboot oem unlock
```
If the device doesn’t automatically reboot, reboot it. It should now be unlocked.
Since the device resets completely, you will need to re-enable USB debugging to continue.

---
### Flashing additional partitions

1.  Download the following files from  [here](https://download.lineageos.org/devices/kebab).
    -   dtbo.img
    -   vbmeta.img
2.  Power off the device, and boot it into bootloader mode:
    -   With the device powered off, hold  **Volume Up  +  Volume Down  +  Power**.
3.  Flash the downloaded image files to your device by typing:
	```
	fastboot flash dtbo dtbo.img
	fastboot flash vbmeta vbmeta.img
	```

---
### Installing Lineage Recovery

Download [Lineage Recovery](https://download.lineageos.org/devices/kebab). Simply download the latest recovery file, named `recovery.img`
1.  Flash recovery onto your device:
	```
	fastboot flash recovery recovery.img
	```
    
2.  Now reboot into recovery to verify the installation.
    -   Use the menu to navigate to and to select the  `Recovery`  option.

---
### Ensuring all firmware partitions are consistent

1.  Download the  `copy-partitions-20220613-signed.zip`  file from  [here](https://mirrorbits.lineageos.org/tools/copy-partitions-20220613-signed.zip).
2.  Sideload the  `copy-partitions-20220613-signed.zip`  package:
    -   On the device, select “**Apply Update**”, then “**Apply from ADB**” to begin sideload.
    -   On the host machine, sideload the package using:
	```
	adb -d sideload copy-partitions-20220613-signed.zip
	```
3.  Now reboot to recovery by tapping “**Advanced**”, then “**Reboot to recovery**”.

---
### Installing LineageOS ROM from recovery

1.  Download the  [LineageOS zip file](https://download.lineageos.org/devices/kebab)  that you would like to install or  [build](https://wiki.lineageos.org/devices/kebab/build)  the package yourself.
2.  If you are not in recovery, reboot into recovery:
    -   With the device powered off, hold  Volume Down  +  Power.
3.  Now tap  **Factory Reset**, then  **Format data / factory reset**  and continue with the formatting process. This will remove encryption and delete all files stored in the internal storage, as well as format your cache partition (if you have one).
4.  Return to the main menu.
5.  Sideload the LineageOS  `.zip`  package but  **do not reboot**  before you read/followed the rest of the instructions!
    -   On the device, select “**Apply Update**”, then “**Apply from ADB**” to begin sideload.
    -   On the host machine, sideload the package using:
 	```
	adb -d sideload lineage-21.0-XXXXX-nightly-kebab-signed.zip
	```

<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #31708f; background-color: #d9edf7; border-color: #bce8f1;">Normally, adb will report `Total xfer: 1.00x`, but in some cases, even if the process succeeds the output will stop at 47% and report `adb: failed to read command: Success`. In some cases it will report `adb: failed to read command: No error` or `adb: failed to read command: Undefined error: 0` which is also fine."</div>

---
### Installing Add-Ons (Google Apps, Magisk...)

1.  Click  “**Apply Update**”, then “**Apply from ADB**” to begin sideload.
    -   On the host machine, sideload the package using:
 	```
	adb -d sideload filename.zip
	```
    When presented with a screen that says  `Signature verification failed`, click  `Yes`. It is expected as add-ons aren’t signed with LineageOS’s official key!

---

Once you have installed everything successfully, you can now reboot your device into the OS for the first time!

-   Click the back arrow in the top left of the screen, then “**Reboot system now**”.


<div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #31708f; background-color: #d9edf7; border-color: #bce8f1;">**Note:** The first boot usually takes no longer than 15 minutes, depending on the device.</div>

---
**Specs**
CPU: Qualcomm® Snapdragon™ 865  
5G Chipset: X55  
GPU: Adreno 650  
RAM: 8GB/12GB LPDDR4X or LPDDR5  
Storage: 128GB/256GB UFS 3.1 2-LANE  
Battery: 4,500 mAh (2S1P 2,250 mAh, non-removable)  
Warp Charge 65W (10V/6.5A)

**Camera**
-   Main Camera
    Sensor: Sony IMX586  
    Megapixels: 48  
    Pixel Size: 0.8µm/48 MP, 1.6µm/12 MP four in one  
    Lens Quantity: 6P  
    OIS: Yes  
    EIS: Yes  
    Aperture: f/1.7
    
-  Ultra Wide Angle Lens
    Megapixels: 16  
	Aperture: f/2.2  
	Field of View: 123°
	
-   Macro Lens
	Megapixels: 5
-   Monochrome Lens
	Megapixels: 2
-	Autofocus
	Multi Autofocus (PDAF+CAF)

- Front Camera
	Sensor: Sony IMX471  
	Megapixels: 16  
	Pixel Size: 1.0 µm  
	EIS: Yes  
	Autofocus: Fixed Focus  
	Aperture: f/2.4  

- Features
	Face Unlock, HDR, Screen Flash, Face Retouching  

**Display**
-   Parameters
	Size: 6.55 inches (measured diagonally from corner to corner)  
	Resolution: 2400 x 1080 pixels 402 ppi  
	Aspect Ratio: 20:9  
	Type: 120 Hz Fluid AMOLED  
	Support sRGB, Display P3  
	Cover Glass: Corning® Gorilla® Glass  

**Connectivity**
- LTE/LTE-A
	4×4 MIMO, Supports up to DL Cat 20/UL Cat 18 (2.0Gbps /200Mbps), depending on carrier support
- Band
    GSM: B2, 3, 5, 8  
    WCDMA: B1, 2, 4, 5, 8, 9, 19  
    LTE-FDD: B1, 2, 3, 4, 5, 7, 8, 12, 13, 17, 18, 19, 20, 25, 26, 28, 32, 66  
    LTE-TDD: B34, 38, 39, 40, 41, 42  
    5G NSA: N1, 3, 7, 28, 41, 78  
    5G SA: N41, 78  
    MIMO: LTE: B1, 3, 7, 38, 41; NR: N1, 3, 7, 78
- Wi-Fi
	2×2 MIMO, Support 2.4G/5G, Support WiFi 802.11 a/b/g/n/ac/ax
- Bluetooth
	Bluetooth version 5.1, support aptX & aptX HD & LDAC & AAC
- GPS
	GPS (L1+L5 Dual Band), GLONASS, Galileo (E1+E5a Dual Band), Beidou, A-GPS
- NFC
- Ports
    USB 3.1 GEN1  
    Type-C  
    Support standard Type-C earphones  
    Dual nano-SIM slot

**Audio** 
- Dual Stereo Speakers  
    Noise cancellation support  
    Dolby Atmos®

[![Qualcomm Snapdragon 865](https://res.cloudinary.com/marcomontalbano/image/upload/v1729955140/video_to_markdown/images/youtube--cDxBXgE8D-g-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=cDxBXgE8D-g "Qualcomm Snapdragon 865")
