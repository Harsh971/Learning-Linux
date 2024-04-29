# Soft Links in Linux

## Description

A Symbolic link, also known as a Soft link or Symlink, is a special type of file that points to another file or directory in the filesystem. Unlike a hard link, which points directly to the inode of the target file, a symbolic link contains the pathname of the target file.

## Here's a breakdown of some key characteristics of soft links:

- <b>Reference to Another File or Directory:</b> A symbolic link is essentially a pointer to another file or directory. It can be used to reference files and directories across different locations in the filesystem.
- <b>Differentiation from Hard Links:</b> Unlike hard links, which directly reference the inode of the target file, symbolic links reference the pathname of the target file. This means that if the target file is moved or renamed, the symbolic link will still point to the correct target as long as the relative path remains valid.
- <b>Symbolic Link Representation:</b> When you list the contents of a directory using ls -l, symbolic links are indicated by an 'l' at the beginning of the file permissions section. The output will show the symlink's name, permissions, owner, group, size, creation date, and the path to the target file or directory.
- <b>Usage:</b> Symbolic links are commonly used for various purposes, such as:
  - Creating shortcuts to frequently accessed files or directories.
  - Simplifying directory structures by providing alternative access points.
  - Allowing compatibility between different versions of software by pointing to specific libraries or configurations.
  - Facilitating the separation of data and application files by providing symbolic links to shared directories.
- <b>Permissions and Ownership:</b> Symbolic links have their own permissions and ownership settings, separate from the target file or directory.

## Instructions :

- Create a file named test.txt with text "Hello" stored in it
```
echo "Hello" > test.txt
```
- We will create a Soft Link using the following notation
```
# ln -s path-to-target  path-to-link

ln -s test.txt testfolder/testshortcut.txt
```
- We can verify that unlike HardLink, here we have Links : 1 in stat command
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/Soft%20Link/image1.png"></img>
