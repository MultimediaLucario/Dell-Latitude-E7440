
![2 repository-open-graph-template](https://user-images.githubusercontent.com/72415505/156626233-896a46e1-5bb6-472e-a15e-863ab502352c.png)


# Dell Latitude E7440
If you also own a Dell Latitude E7440 then you can use this EFI Configuration in your E7440 after installing Hackintosh Mojave.
You can download Hackintosh Mojave from `getintopc.com` I have used `Niresh Hackintosh Mojave` for reference you can use the same.

If you want to run macOS Big Sur use the USB creation method here: https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html#downloading-macos

If you don't know anything about what Hackintosh is then you must read about it on Google.

# Note
I have added Clover and Opencore Configurations as per model Dell Latitude E7440 but opencore is in beta stages so I would recommend to use the Clover Boootloader.
The opencore cofiguration only works with macOS Catalina and macOS Big Sur but I doubt it will run perfectly. OC = Opencore && Clover = Clover 

# Steps to hackintosh using the OpenCore Bootloader

To start you'll need the following:

4GB USB Stick

For USB larger than 16 GB to format in FAT32 use Rufus method

macrecovery.py (opens new window)

This will require Python installed (opens new window)
#

1. To grab legacy installers is super easy, first grab a copy of OpenCorePkg (opens new window) and head to /Utilities/macrecovery/. Next copy the folder path for the macrecovery folder. 

<img width="974" alt="file-path 0aea4278" src="https://user-images.githubusercontent.com/72415505/156628158-190cba5d-6114-4972-aa83-f1b14749e34d.png">


2. From here, you'll want to open up a Command Prompt and cd into the macrecovery folder that we copied earlier:

cd Paste_Folder_Path

<img width="917" alt="command-prompt 53392eba" src="https://user-images.githubusercontent.com/72415505/156628358-c2692037-80ac-40f9-bb3b-9a424442dafe.png">

3. Now run one of the following depending on what version of macOS you want(Note these scripts rely on Python (opens new window) support, please install if you haven't already):

 Lion (10.7):
python macrecovery.py -b Mac-2E6FAB96566FE58C -m 00000000000F25Y00 download
python macrecovery.py -b Mac-C3EC7CD22292981F -m 00000000000F0HM00 download

 Mountain Lion (10.8):
python macrecovery.py -b Mac-7DF2A3B5E5D671ED -m 00000000000F65100 download

 Mavericks (10.9):
python macrecovery.py -b Mac-F60DEB81FF30ACF6 -m 00000000000FNN100 download

 Yosemite (10.10):
python macrecovery.py -b Mac-E43C1C25D4880AD6 -m 00000000000GDVW00 download

 El Capitan (10.11):
python macrecovery.py -b Mac-FFE5EF870D7BA81A -m 00000000000GQRX00 download

 Sierra (10.12):
python macrecovery.py -b Mac-77F17D7DA9285301 -m 00000000000J0DX00 download

 High Sierra (10.13)
python macrecovery.py -b Mac-7BA5B2D9E42DDD94 -m 00000000000J80300 download

 High Sierra (10.13) (Alternate Command)
python macrecovery.py -b Mac-BE088AF8C5EB4FA2 -m 00000000000J80300 download

 Mojave (10.14)
python macrecovery.py -b Mac-7BA5B2DFE22DDD8C -m 00000000000KXPG00 download

 Catalina (10.15)
python macrecovery.py -b Mac-00BE6ED71E35EB86 -m 00000000000000000 download

 Big Sur (11)
python macrecovery.py -b Mac-42FD25EABCABB274 -m 00000000000000000 download

This will take some time, however once you're finished you should get either BaseSystem or RecoveryImage files:

![macrecovery-after 4c24ba88](https://user-images.githubusercontent.com/72415505/156629881-3d0e18a5-79cf-465e-a054-44b39a77b47f.jpg) <img width="973" alt="basesystem-example 93778929" src="https://user-images.githubusercontent.com/72415505/156629925-77869c1f-19ee-463f-bcc7-cafb2be09866.png">

4. Download [Rufus](https://rufus.ie/en/), set the BOOT selection as not bootable, set File System as Large FAT32, click Start, and delete all file autorun in USB Drive partition.

![format-usb-rufus 43feba9e](https://user-images.githubusercontent.com/72415505/156631083-73e33087-d51e-42e4-a804-e93afad7c2ca.png)

5. Next, go to the root of this USB drive and create a folder called com.apple.recovery.boot. Then move the downloaded BaseSystem or RecoveryImage files. Please ensure you copy over both the .dmg and .chunklist files to this folder:

<img width="824" alt="com-recovery 805dc41f" src="https://user-images.githubusercontent.com/72415505/156631343-529ca3ee-9e79-4e21-bab1-7305b4ed3df9.png">

6. Open up and extract the EFI folder archive you downloaded earlier.

7. Copy the folder that's named, "EFI," to the root of your USB Drive.

8. Restart your computer.

9. Open BIOS and disable all the security options.

10. Boot via your Flash Drive.

11. Boot Hackintosh installer.

12. Now open Disk Utility and format your internal or external Hard Drive or SSD as APFS.

13. Install macOS.

14. Your system might boot during the install.

15. Now after install again boot into your usb drive but now boot into the drive in which you installed your Hackintosh.

16. Open Clover Configurator and Mount the EFI partition of the drive you want to boot off of.

17. Now copy my EFI Folder and overrite it with the one system created.

18. Now try booting macOS without the USB drive.

19. Congratulations, you've successfully hackintoshed your Dell Latitude E7440.

# Steps to install Hackintosh 
1. You need to ensure hardware compatibilty if you don't own a Dell Latitude E7440.
2. You must have a USB which is more than 8Gib or atleast 8Gib.
3. Download and install `TransMac` from the link from here `https://www.acutesystems.com/scrtm.htm`.
4. Download the Niresh Hackintosh Mojave `dmg` from `https://getintopc.com/softwares/operating-systems/niresh-mojave-hackintosh-dmg-free-download-1726447/` this link.
5. Open Transmac as administrator and connect your USB Flash Drive.
6. After that Rightclick on the Flash Drive you inserted in the Transmac list and Format the drive for mac.
7. Now again Rightclick and click Restore option and locate the Hackintosh DMG you downloaded.
8. Now after this is done it might take a while sit and relax.
9. Restart your laptop and before that just copy my git files.
10. Open BIOS and disable all the security options.
11. Boot via your Flash Drive.
12. Boot Hackintosh installer.
13. Now open Disk Utility and format your internal or external harddrive/ssd for MAC as APFS partition type.
14. Install the Mac.
15. Your system might boot during the install.
16. Now after install again boot into your usb drive but now boot into the drive in which you installed your Hackintosh.
17. Setup your Hackintosh via offline installer.
18. As wifi will not work so after this connect Ethernet and download Clover Configurator.
19. Open Clover Configurator and Mount the EFI partition of the Drive your installed your Hack on.
20. Now copy my EFI Folder and overrite it with the one system created.
21. You have created your Hackintosh successfully.
22. Now try booting in your Hac without USB.
23. If something doesnot work then search for the respective `kexts` i.e. drivers.

# Good Luck
# On My Laptop everything works except Wifi and Bluetooth.

# List of the kexts which can be usedful 
Appleps2controller

Lilu

USBinjectall

Whatevergreen

AppleALC 

FakePCIID_Intel_HD_Graphics

SMCBatterymanager

BrcmFirmwarerepo

Brcmpatchram

CodecCommander

DisableTurboBoostBattery

