################################################################

Note: 
1. Use the compatibility query tool http://support.huawei.com/onlinetoolweb/ftca/en to obtain the compatibility between the server and OS compatibility & components and OS, 
and then use the driver mapping table to query the mapping relationship.

2. Please upload the driver to the OS directory and then perform the installation

3. Please use the user with administrator rights for driver maintenance.

#################################################################

1. Load the ISO or img driver file during OS installation.

1.1 image file Loading method :
    *.iso --- using the Virtual CD/DVD
    *.img --- using the Virtual Floppy

1.2 Application Description
	1) The RAID driver needs to be loaded when the OS is installed on the hard disk of the RAID controller card.
	2) SAN Boot Start the OS to load the FC card driver.
	
1.3 Guide to Loading Image Files
	For details, see the operating system installation guide.
	https://forum.huawei.com/enterprise/en/huawei-server-os-installation-guides-summary/thread/407583-895
	


################################################################

2. After the OS is installed, install the driver file in onboard_driver_XXX.iso
onboard_driver_xxx.iso driver file list and manual driver installation guide:
NIC-CX4-Lx-Win2K22--1-x86_64_silence.exe
---SP333 CX4 driver
#Note：Please replace the xxx.tgz with the archived package name for the actual driver installation,
#Upgrade installation:
1. rpm -Uvh xxx.rpm
2. rmmod txgbe;modprobe txgbe;
3. modinfo txgbe |grep -i version
#Downgrade Installation:
1. rpm -Uvh xxx.rpm --oldpackage
2. rmmod txgbe;modprobe txgbe;
4. modinfo txgbe |grep -i version
	 