# Learning Log

Documenting practical IT experience gained through home lab experimentation, personal and family device troubleshooting, and independent technical learning in addition to structured coursework.

---

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
