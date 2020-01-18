#Unraid Tips and Tweaks

##USB Controller Passthrough.

Single usb controller on the asus x570 prime pro so we need to stub out invididual buses 

Add the following to /boot/config/vfio-pci.cfg 
BIND=06:00.3 06:00.1 0c:00.4

Currently binding 06:00.3 to the Windows gaming VM

##SATA Passthrough
Using vfio-pci.ids to pass whole sata controller. 
TODO: identify specific bus on that to pass thruogh so other ports can be passed through somewhere else
append vfio-pci.ids=1022:7901 initrd=/bzroot


##HDMI Problems
Enabled MSI interrupts witht he MSI Utility v2
https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/

Occasionally windows update might undo these changes so if sound starts sounding corrupt important to check this first. 

Changing sampling frequency can also resolve issue at times
