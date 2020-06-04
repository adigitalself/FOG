## Welcome to the SunSSC OS Deployment Guide
### Using F.O.G. (Free Open-source Ghost)
![FOG](./maxresdefault.jpg)

## [Video of a image/software deployment in action](https://web.microsoftstream.com/video/e0257dac-b739-4541-8de1-fa4f72231292)

### Pre-Requisites
- A new hostname for the computer
- Correct BIOS settings
- Ethernet connection to 192.168.16.0/21 subnet
- Recommend doing immediately after receiving from Dell

### Required BIOS Config (May differ between models)
- UEFI Boot Path Security set to **Always,Except Internal HDD&PXE**
- Integrated NIC: **Enable UEFI Network Stack**
- Secure Boot **disabled**
- SATA Operation set to **AHCI**
- Onboard NIC enabled w/PXE and **at top of Boot Sequence**

### Image Deployment
1. The new computer should now boot into the PXE fog menu (you have three seconds!)
2. Select _


### Register the Computer's in F.O.G.
3. Set the correct BIOS settings
4. Once the computer boots into NIC PXE ROM, select _Perform Full Host Registration and Inventory_

### Registration and Image Deployment
1. Select _Perform Full Host Registration and Inventory_ in the FOG PXE boot screen
2. "Enter hostname for this computer": Enter your chosen new hostname
3. "Enter the image ID to associate with computer (? for listing)": Select W10ProUEFI (1) or W10ProLegacy (2) for a sysprepped image.
4. "Would you like to associate this host with groups?": N
5. "Would you like to associate this host with snapins?": N
6. "Would you like to associate a product key to this host?": N
7. "Would you like this host to join a domain, (using default settings)?": Y
8. "Enter the primary user for this computer": (leave blank)
9. "Enter the other tag for this computer": (leave blank)
10. "Would you like to deploy image to this computer now?": Y
11. Enter username/password

### Software Deployment
- FOG will join the computer with your chosen hostname to "sunssc.local\_SUNSSC\PDQ" OU in AD
- PDQ will deploy 7zip, Adobe, Chrome, etc. to computer

### Next Steps
- Move the computer to the needed domain & OU
- Write an AD description for computer

_Written June 2nd, 2020 by DK_
