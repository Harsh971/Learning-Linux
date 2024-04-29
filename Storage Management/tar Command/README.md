# tar Command in Linux

## Description

The tar command in Linux is used to create, manipulate, and extract tar archives. A tar archive is a single file that contains multiple other files and/or directories. The name "tar" stands for "tape archive," which reflects its historical use for creating backups on magnetic tape. Here's an overview of the tar command and its functionalities:

## Basic Structure :
```
tar  [options]  [archive-file]  [file1 file2 ...]
```
- **[options]:** Various options that modify the behavior of the tar command.
- **[archive-file]:** Specifies the name of the tar archive file to create, manipulate, or extract.
- **[file1 file2 ...]:** Specifies the files and/or directories to include in or extract from the tar archive.

## Common Options :
- **-c, --create:** Create a new tar archive.
- **-x, --extract:** Extract files from a tar archive.
- **-f, --file=ARCHIVE:** Specifies the filename of the tar archive.
- **-v, --verbose:** Print the names of files being processed.
- **-z, --gzip:** Compress or decompress the archive using gzip.
- **-j, --bzip2:** Compress or decompress the archive using bzip2.
- **-J, --xz:** Compress or decompress the archive using xz.
- **-t, --list:** List the contents of a tar archive.
- **-r, --append:** Append files to an existing tar archive.
- **-u, --update:** Append files to an archive only if they are newer than the copy in the archive.
- **-A, --catenate:** Concatenate multiple tar archives into one.
- **-C, --directory=DIR:** Change to the specified directory before performing any operations.
- **--remove-files:** Remove files after adding them to the archive.


## Examples:

1.  Create | Append a File into archive.tar
<br><img src="https://github.com/Harsh971/Learning-Linux/blob/main/Storage%20Management/tar%20Command/image1.png"><br><br>

2. Extract Using tar
```
tar  --extract  --file  archive.tar 
OR
tar  xf  archive.tar
```
