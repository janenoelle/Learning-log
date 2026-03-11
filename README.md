# Learning Log

Documenting practical IT experience gained through home lab experimentation, personal and family device troubleshooting, and independent technical learning in addition to structured coursework.

---
### HDD Recovery and Configuration - March 2026

**Problem**

While experimenting with a Linux bootable USB drive, a 1TB internal HDD appeared as unallocated and formatted as RAW in Windows Disk Management, making the drive unusable.

**Actions**

* Verified the drive status in Windows Disk Management, which reported the drive as healthy.
* Opened the laptop to physically confirm the drive was installed correctly and performed a quick internal clean of the fan. 
* Reformatted the drive from RAW to NTFS to make it compatible with Windows.
* Allocated a drive letter to mount the drive.
* Renamed the drive for easier identification.
* Tested functionality by copying files to the drive to confirm read/write capability.
* Confirmed the drive appeared correctly in File Explorer and operated normally.

**Result**

The 1TB HDD is now fully operational and has been configured for use as storage for virtual machines.

**Skills Used**

* Troubleshooting storage and disk allocation issues
* Filesystem formatting and disk configuration
* Basic hardware inspection and laptop maintenance
* Verifying system changes through functional testing

**Tools Used**

* Windows Disk Management
* Windows File Explorer
* Bootable Linux USB environment
* Physical hardware inspection

## Creating a Bootable Linux USB & Investigating a Mystery 1TB Hard Drive – March 2026
### Problem

As part of my studies for the Google IT Support Professional Certificate, I wanted to practice working with the Linux terminal in a real environment. Because my primary SSD is only 256GB, I chose to create a bootable Linux USB live environment rather than a dual-boot setup, avoiding the need to repartition limited SSD space.

During this process I noticed a discrepancy in reported storage: Windows showed only the 256GB SSD, while Linux disk management suggested that an additional unused 1TB drive might also be present.

### Action

Downloaded the Linux Mint Cinnamon ISO and used Rufus to create a bootable USB flash drive. Booted the system into the Linux live environment via the boot menu, allowing Linux to run directly from the USB without altering the existing Windows installation.

While examining disk information within the Linux environment, I identified evidence of an additional 1TB internal hard drive that was not visible within Windows.

After returning to Windows, I investigated further using disk management tools and discovered the drive existed but was formatted as RAW, meaning it had no recognised filesystem and therefore could not be mounted or used by Windows.

This occurred because the drive had previously been installed when a friend upgraded the laptop’s RAM but had not been fully configured afterwards.

To verify the hardware, I opened the laptop and confirmed the physical presence of the 1TB hard drive. While the laptop was open, I also cleaned dust from the cooling fan to improve airflow. After rebooting into Windows, I checked the drive's health status using Windows system tools.

### Result

Successfully created a working bootable Linux USB and gained experience booting into a Linux live environment without modifying the installed operating system.

The investigation also revealed the presence of an unused 1TB internal hard drive that had been left in RAW format and therefore remained unusable within Windows. The drive’s existence and condition were confirmed through both software inspection and physical hardware verification.

### What I Learned

- How to create a bootable Linux USB using Rufus
- How to boot into a Linux live environment without modifying the installed OS
- Practical exposure to the Linux terminal while running a live environment
- The difference between RAW and NTFS disk formats in Windows
- That storage devices may exist but remain unusable until properly initialised and formatted
- How Linux tools can help identify hardware that is not immediately visible in Windows
- Basic laptop hardware inspection and maintenance (verifying components and cleaning cooling fans)

## Android Tablet Debloat – Feb 2026

### Problem

An older Android tablet contained numerous preinstalled applications that created interface clutter. The device was being repurposed exclusively for media consumption, so the goal was to remove non-essential applications while maintaining operating system stability.

### Action

Enabled Developer Options and USB debugging, then used Android Platform Tools (ADB) via Command Prompt in Windows 11. Initially followed guided command usage to list installed packages and uninstall non-essential apps. Through repeated use, I recognised the structure of ADB commands and Android package naming conventions.

Used commands such as:

adb shell pm list packages | findstr keyword  
adb shell pm uninstall --user 0 com.packagename*

As I became more familiar with package naming patterns, I identified that Google-branded packages were generally safer removal targets than core Android system packages (com.android.*), which are more tightly integrated with the OS. I adjusted my approach accordingly to reduce risk of system instability and rebooted the device to allow reindexing and optimisation.

### Result

Improved usability and visual clarity of the interface. The tablet now functions as a streamlined media device without unnecessary applications.

### What I Learned

- Practical use of ADB for package management  
- How to open Command Prompt directly within a working directory in Windows 11  
- Recognition of Android package naming conventions  
- Importance of distinguishing between Google applications and core Android system packages  
- Greater awareness of system dependencies and safe modification practices  
