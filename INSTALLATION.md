# INSTALLATION

## Download Big Sur 

Run this command on Temrinal:

    sudo /System/Library/PrivateFrameworks/Seeding.framework/Resources/seedutil enroll DeveloperSeed

Go to System Updater and download the Install macOS Beta app.

## Create bootable ISO file

    hdiutil create -size 12G -fs hfs+ -volname install -type SPARSEBUNDLE ~/Desktop/install
    hdiutil attach ~/Desktop/install.sparsebundle
    sudo /Applications/Install\ macOS\ Beta.app/Contents/Resources/createinstallmedia --volume /Volumes/install --nointeraction
    hdiutil detach `diskutil list |grep 'Install macOS Beta' |awk '{print $8}'` -force
    hdiutil makehybrid -o ~/Desktop/install ~/Desktop/install.sparsebundle
    rm -rf ~/Desktop/install.sparsebundle

## Create the virtual machine and install to disk/SSD
Download and install the trial version of the VMware Fusion from their site. I'm used the version 11.5.5.

- Create a custom virtual machine
    ![](Screenshot/BigSur/Installation/create_custom_vm.png)

- Operating System: Apple OS X - macOS 10.15
    ![](Screenshot/BigSur/Installation/select_os.png)

- Create a new virtual disk (The size doesn't matter, We'll delete later)
    ![](Screenshot/BigSur/Installation/create_new_disk.png)

- Click in "Customize Settings"
    ![](Screenshot/BigSur/Installation/custommize_settings.png)

- Save the VM on desktop with name: bigsur
    ![](Screenshot/BigSur/Installation/save_name.png)

- Insert the spare disk/SSD on PC (reboot if necessary) and identify what /dev/diskX is.

You can look on Disk Utility.app:
    ![](Screenshot/BigSur/Installation/disk_utils.png)

- Create VMDK that point to it:
    
    `sudo diskutil unmountDisk diskX /Applications/VMware\ Fusion.app/Contents/Library/vmware-rawdiskCreator create /dev/diskX fullDevice ~/Desktop/bigsur.vmwarevm/physical sata`

- Edit the virtual machine settings created previously
    ![](Screenshot/BigSur/Installation/bigsur_settings.png)

- Click in Hard Disk (SATA) and delete it (Remove Hard Disk)
    ![](Screenshot/BigSur/Installation/remove_hard_disk.png)

- Then add the physical disk
    ![](Screenshot/BigSur/Installation/add_existing_hard_disk.png)

- There's a bug in Fusion. To select the physical.vmdk, right click then "Quick Look", then "Share virtual disk with the virtual machine that created it"
    ![](Screenshot/BigSur/Installation/select_physical_disk.png)

- Click Apply.
    ![](Screenshot/BigSur/Installation/apply_physical_disk.png)

- Mount the install.iso
  ![](Screenshot/BigSur/Installation/mount_iso.png)
  ![](Screenshot/BigSur/Installation/connect_cd.png)

- Start the VM and install as usual until: Disk Utility, format GUID with APFS (VMware Virtual SATA Hard Drive Media), Install macOS, wait few reboots and stop at first boot wizard.

    **Warning**: This can take up to 45 minutes. It may seem like it is stopped, but it is not.

![](Screenshot/BigSur/Installation/boot_screen.png)

- Press Command + Q and shutdown (usually WIN + Q)
![](Screenshot/BigSur/Installation/shutdown_vm.png)
- Close VMware Fusion.

## Copy OpenCore to EFI
Mount the EFI with:
    
    sudo diskutil mount diskXs1

## Done
Boot from the new disk/SSD and finish de first boot wizard.


# Thanks
- [ludufre](https://www.insanelymac.com/forum/topic/344299-guide-gigabyte-ga-z370n-wifi-i7-8700k-uhd-630-big-sur-110-dp1/)



