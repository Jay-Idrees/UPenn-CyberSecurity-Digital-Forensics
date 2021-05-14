# Digital and Network Forensics


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


## Types of memory storage

- Mechanical hard drives
- Flash storage e-g USB - Allows quicker read and write access
- SSD - warrants caution as data can be wiped out very quickly
- SD or microSD cards

Note that USBs SSD and SD cards use similar type of technologies and are considerd **non-volatile** as they hold data even when not connected to power


## Digital forensics types and methodologies

- Email Forensics 

- Mobile Device Forensics

- Network Forensics Uses wireshark, Snort

- Memory Forensics - Different from disk Forensics as it also investigates volatile memory

- Computer Forensics 

## Digital Forensic Framework

1.` Prepration` for an Investigation - Incident remote or local, what laws are relevant

2. `Collection` of Evidence / Forensic Recovery - What data to collect and the best way to collect it.

3. `Preservation` of Evidence - A read only master is made and stored in a digital valt, all processing is done on a copy. A **Write blocker** is used to prevent data contamination. In addition, a **cryptogenic digest** or **hash** is created for data integrity to ensure that the evidence is not altered during the investigative process

4. Electronic Discovery and `Analysis` - Document: Time, Date, location and applications used. The Evidence must be reporducible

5. Presentation and `Reporting`


## Example Case

# Autopsy Workflow

**Autopsy** is a software this is used to perform foreisic analysis. The workflow for using the autopsy software is as below:

- **Create a case**
- **Add an Image**
- **Configure Ingest Modules** - helps with categorization and labeling of the evidence
- **Ingest in Progress** - Its the process of loading the .E01 file into Autopsy
- **Manual Analysis** - Manually searching through the file system
- **Create a Timeline** - Creating a timeline of events
- **Report**

# Extracting data from an iPhone

- Has two partitions: **root**- contains operating system level functions and **var** contains user data

- Data is first copied using the bit level which recovers deleted messages  as well as GPS coordinates and cell tower locations

- Iphone also alows to back up their data to the cloud

- Cloud Challanges  - Isolating and securing the evidence is challenging when data is in multiple locations. Also, SLAs must be recognized when dealing with other companies, in addition to other legal issues.

- Important Directories
  - `/mobile`
  - `/Applications`
  - `/Library`
  - `/root`
  - `/Logs`
  - `/logs`

 - The iPhone's directory structure is similar to Linux because it is Unix based.

 - The data is stored in SQL (Structure Query Language) databases. The following are the database files

 - These are the main databases that applications such as mail, SMS, calendar, and the address book use:
 
  - `AddressBook.sqlitedb` contains contact information and personal data like name, email address, etc.

  - `AddressBookImages.sqlitedb` contains images associated with saved contacts.

  - `Calendar.sqlitedb` contains calendar details and events information.

  - `CallHistory.db` contains incoming and outgoing call logs including phone numbers and time stamps.

  - `sms.db` contains text and multimedia messages along with their time stamps.

  - `voicemail.db` contains voicemail messages.

  - `Safari/Bookmarks.db` contains saved URL addresses.

  - `Envelope Index` contains email addresses.

  - `consolidated.db` contains GPS tracking data.

  - `locationd` contains the Google coordinates of places.
 
 iPhones also have data stored in `plists`, or `property lists`. A `plist` stores configuration information, call history, and cache information (i.e., websites visited).
 
  - `Maps/History.plist` keeps track of location searches.

  - `Maps/Bookmarks.plist` contains bookmarks.

  - `Safari/History.plist` contains internet browsing history.
    - `/logs` and `/Logs` contain device information.


- `History.plist` stores iphone browsing history

- `File metadata` tab in data content 