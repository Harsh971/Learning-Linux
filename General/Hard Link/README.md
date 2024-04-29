# Hard Links in Linux

## Description

Hard links are commonly used to create multiple references to the same file without duplicating its contents, which can be useful for versioning systems, backup utilities, and efficient file management. However, their direct connection to inodes and data blocks also means that they cannot reference directories or files across different filesystems and are subject to certain limitations compared to symbolic links.

## Here's a breakdown of some key characteristics of hard links:

- <b>Same Inode:</b> When you create a hard link to a file, both the original file and the hard link(s) point to the same inode. An inode is a data structure in a Unix-style file system that stores all the metadata about a file (e.g., permissions, owner, size, timestamps).
- <b>Same Data Blocks:</b> Since hard links point to the same inode, they also reference the same data blocks on the disk. This means that modifying the content of one file will affect all hard links pointing to the same inode because they share the same underlying data.
- <b>No Distinction:</b> There is no practical difference between the original file and its hard links. All links are equal in terms of their access permissions, ownership, and other attributes.
- <b>Filesystem Limitations:</b> Hard links can only be created within the same filesystem. You cannot create a hard link that points to a file on a different filesystem.
- <b>Removing Links:</b> Deleting a hard link does not remove the actual file's data until all hard links to that inode are deleted. The data will be retained as long as there's at least one hard link remaining.

## Instructions :

- Create a file named test.txt with text "Hello" stored in it
```
echo "Hello" > test.txt
```
- View the inode and Links associated with the file through the following command
```
stat test.txt
```
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/Hard%20Link/image1.png"></img>
- We create a directory where we will store the Hard Link File
```
mkdir testfolder
```
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/Hard%20Link/image2.png"></img>
- We will create a Hard Link of the existing file to a non existing location
```
# path-to-target  path-to-link

ln test.txt testfolder/test.txt
```
- We can verify the existance of Hard Link establishment through Links : 2 in stat command
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/Hard%20Link/image3.png"></img>
