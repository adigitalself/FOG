# Guide to capturing/cloning a disk image over network using F.O.G.

### F.O.G. is able to not only deploy but also capture/clone disks over the network.

### [Video of an Image Capture in action]()

### Pre-Requisites
- Host registered on F.O.G.
- Correct BIOS settings (see [fog.sunit.io](https://fog.sunit.io))

### Steps
1. Go to the [fogproject server](http://fogproject.sunssc.local/fog)
2. Under the 'Images' tab, select 'Create New Image' and name it. Leave the rest as default.
3. Go to the 'Hosts' tab. If the host is not there, select 'Create New Host' and input the MAC address and name.
4. Select the host and assign the newly created image to the host (in 'Host Image')
5. Select the host and then go to the 'Basic Tasks' tab. Select 'Capture'
6. Tick 'Schedule with shutdown' if you want the computer to shutdown after capture.
7. Turn on the to-be-captured computer.

### Troubleshooting
- Having SATA operation mode as 'RAID' instead of 'AHCI' may cause issues.
- Bitlocker or other data security programs may cause issues.
- If all fails, try creating the image again with the 'image type' as 'Multiple Partition Image' or 'Raw Image'. This will consume more space.
