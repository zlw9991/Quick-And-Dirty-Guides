# Quick-And-Dirty-Guides
A compilation of quick and dirty guides to doing IT-related things.



## Table of Contents  
1. [Cloning windows 10 on GPT Disk to MBR Disk](#cloning-windows-10-on-gpt-disk-to-mbr-disk)
2. [Cloning windows 10 vmware VMDK vm to hyper-V](#win-10-vmware-vm-to-hyper-v)
3. [Increasing Windows Partitions Shrink Space](#increasing-windows-partitions-shrink-space)


<a name="headers"/>


## Cloning windows 10 on GPT Disk to MBR Disk:

IE: Converting a UEFI Windows 10 install to a MBR one etc.

Assumes some understanding of the tools / isos used.

### Prerequisites:

You will need 3 thumbdrives each flashed individually (ie: one item on one thumbdrive each) with the following items:
1. Gparted Linux
2. Hiren's BCD
3. Windows 10 ISO usb

For 1. and 2., use rufus or balana etcher etc. to flash their iso's. For 3. you will need to download window's media creation tool.

Ensure you have two disks: one source disk with the windows 10 GPT partition, and one empty destination disk.

### Steps:

1. Boot into gparted with both disks connected to the boot device, then once the gparted program has been loaded, select the destination disk.
2. In gparted, select 'devices'->'create partition table'->'msdos', click apply and the destination disk will be formatted to MBR (ensure it's empty first!).
3. Then, in gparted, select your source disk. Then select the source disk's windows partition, right click and then click copy.
4. Paste the partition into the destination disk. Hit apply and wait.
5. Once copied to the destination disk, boot into Hiren's BCD.
6. Disconnect the source disk.
7. Inside Hiren's BCD, load up macrium reflect. 
8. In macrium reflect, select the destination disk, then in the upper tabs, select 'Restore'->'Fix Windows Boot Problems'.
9. Go through the default settings by clicking next but be sure the right disk is selected. Refer to [this](https://kb.macrium.com/KnowledgebaseArticle50168.aspx) if unsure.
10. Once done, boot into the windows 10 ISO usb.
11. At the installation menu, select 'repair your computer'.
12. At the blue menu, select 'troubleshoot'->'startup repair'.
13. Wait for it to finish.
14. Once rebooted, windows 10 on the destination MBR disk should be able to boot.


## Win 10 VMware VM to Hyper-V:

### Prerequisites:

1. External Storage with sufficient size to store VM

### Steps:

1. Boot into your 

## Increasing Windows Partitions Shrink Space:

<WIP>
