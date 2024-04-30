# Mounting and UnMounting in Linux

## **1. Mounting :**
Mounting in Linux refers to the process of making a file system accessible to the operating system at a specified location within the directory tree. This allows users and applications to access the contents of storage devices, such as hard drives, USB drives, network shares, and disk images.

### How Mounting Works :
1. Identify the Device:
	- The first step in mounting a file system is identifying the device that contains the file system you want to mount. This could be a physical storage device (like a hard drive partition) or a virtual device (like a disk image file).

2. Choose a Mount Point:
	- Next, you need to choose a directory within the Linux directory tree where you want to access the contents of the mounted file system. This directory is called the "mount point."

3. Mounting the File System:
	- Once you have identified the device and chosen a mount point, you can use the mount command to attach the file system to the specified location. The mount command creates a link between the mount point and the file system on the device.

4. Accessing the File System:
	- After mounting, the contents of the file system become accessible through the mount point. Users and applications can read from and write to files on the mounted file system as if they were part of the local directory structure.

### Example :
1. Identify the Device:
	- You plug in the USB drive, and Linux assigns it the device name **`/dev/sdb1`**.
2. Choose a Mount Point:
	- You decide to mount the USB drive to the directory /mnt/usb.
3. Mounting the File System:
	- You use the mount command to mount the USB drive :
```
sudo mount /dev/sdb1 /mnt/usb
```
4. Accessing the File System:
	- After mounting, you can navigate to /mnt/usb and access the files on the USB drive as if they were stored locally.

### Explanation:
- In the mount command:
	 - **`/dev/sdb1`** is the device file representing the USB drive's partition.
	 - **`/mnt/usb`** is the directory where you want to access the files on the USB drive.
- Once mounted, the USB drive's files and directories become accessible under /mnt/usb.

## Important Notes:
- Always ensure that the mount point directory exists before attempting to mount a file system onto it.
- Use sudo or be logged in as root to execute mount and unmount commands, as they typically require administrative privileges.
- Unmount file systems before removing storage devices to prevent data corruption or loss.

<hr>

## **2. UnMounting :**
Unmounting in Linux refers to the process of detaching a mounted file system from the directory tree, making it inaccessible to the operating system and users. This ensures that all data is written back to the file system and any pending operations are completed before disassociating it from the mount point.

### How Unmounting Works:
1. Identify the Mounted File System:
	- Before unmounting, you need to identify the mounted file system that you want to detach. This is typically done by checking the current mount points using commands like mount or df.

2. Choose the Mount Point:
	 - Once you have identified the mounted file system, you need to specify the mount point (directory) from which the file system is mounted. This is used as the argument for the umount command.

3. Unmounting the File System:
	 - Once you have identified the mount point, you can use the umount command to unmount the file system. The umount command closes any open files, syncs the file system, and disassociates it from the mount point.
 

### Example:

1. Identify the Mount Point:
	 - Weu previously mounted the USB drive to the directory **`/mnt/usb`**.

2. Unmounting the File System:
	 - To unmount the USB drive, you use the **`umount`** command
```
sudo umount /mnt/usb
```

### Explanation:
- In the umount command:
	 - **`/mnt/usb`** is the directory where the USB drive was mounted.
- When you run the umount command, Linux performs the necessary operations to safely detach the file system from the mount point.
- Once unmounted, the directory **`/mnt/usb`** no longer contains the contents of the USB drive, and attempts to access files within it will result in errors until the drive is remounted.

## Important Notes:
- Ensure that no processes or users are accessing files on the file system before unmounting to prevent data loss or corruption.
- Use **`sudo`** or be logged in as root to execute the **`umount`** command, as it typically requires administrative privileges.
- It's essential to properly unmount file systems before physically removing storage devices to avoid potential data loss or damage to the file system.
