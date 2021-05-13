# Network Forensics


  - Forensic backups (system image or bit-level backups)  create an exact replica of all contents contained on the entire hard drive, including slack space, free space, and deleted files.
 
   - Forensic backup images are created in the following formats: 
  
     - **Raw formats:** These formats can be created with programs such as `dd`, `ddfldd`, and `ddcdd`.
       - .bin
       - .dd
       - .img
       - .raw
 
     - **Advanced Forensic Format (AFF):** The AFF format is for disk images and related forensic metadata.
       - .AFF
       - .AFF4

- One concern with working with live systems is that the data can get lost if there is powerloss and there is always a risk that there is a hacker who maybe trying to get into the system, waiting for someone to logback in

  - A **write blocker** is a device that allows anything connected to it to perform only read operations, therefore preventing the drive from being written to and overwriting  evidence.
 
 You may encounter the following file systems during an investigation:

   - **New Technology File System (NTFS):** Supported under Windows 10, 8, 7, Vista, XP, and NT.
 
   - **File Allocation Table (FAT):** Supported by older and newer versions of Windows.
 
   - **Apple File System (AFS):** Used by Mac OS systems.
 
   - **Fourth Extended File System (Ext4):** Used in most Linux distributions.