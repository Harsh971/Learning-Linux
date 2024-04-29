# File Permissions in Linux

## Description

File permissions determine who can read, write, and execute a file or directory. These permissions are essential for maintaining security and controlling access to files and directories on a system. The chmod command is used to change these permissions.file permissions determine who can read, write, and execute a file or directory. These permissions are essential for maintaining security and controlling access to files and directories on a system. The chmod command is used to change these permissions.

## File Permissions :
In Linux, file permissions are divided into three categories: owner, group, and others.

- <b>Owner (user):</b> The user who owns the file or directory.
- <b>Group:</b> The group associated with the file or directory.
- <b>Others:</b> Everyone else who has access to the system.
<br><img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/File%20Permissions/image1.png"></img>

## Each category has three types of permissions:
- <b>Read (r):</b> Allows the reading of a file's contents or listing of directory contents.
- <b>Write (w):</b> Allows the modification of a file's contents or creation/deletion of files within a directory.
- <b>Execute (x):</b> Allows the execution of a file as a program or the traversal of a directory.

## Each permission has a corresponding numeric value:
- Read (r) = 4
- Write (w) = 2
- Execute (x) = 1
<br><br>You add these values to set permissions.
<br><img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/File%20Permissions/image2.png"></img>

We can use the chmod command as follows to modify File Permissions
```
chmod [mode] filename
```
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/File%20Permissions/image3.png"></img>


