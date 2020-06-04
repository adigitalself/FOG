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
The new computer should now boot into the PXE fog menu (you have three seconds!)
1. Select _Perform Full Host Registration and Inventory_ in the menu
2. "Enter hostname for this computer": Enter your chosen new hostname
3. "Enter the image ID to associate with computer (? for listing)": Select W10UEFI (3) for a sysprepped Windows 10 Professional image.
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
- PDQ will deploy 7zip, Adobe, Chrome, Report Requirements (Sql Clr & .net 2010), dell firmware updates.
- Computer should get the rest of the settings from GPOs and windows updates from WSUS.
- Check activation status to be sure.
- Label the computer.
- You are done until the computer is being deployed!


### Final Steps
- Place computer object in the correct Active Directory OU and department
- Enter a meaningful description in AD and in the asset management system 
- Install software that need licenses (e.g. anti-virus, Office, remote assist tools, vpn, etc.)

_Written June 2nd, 2020 by DK_
_Updated June 4th, 2020_
