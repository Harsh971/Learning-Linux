# Applying Filters to Files

## Description

The find command in Linux is a powerful utility used to search for files and directories within a specified directory hierarchy based on various criteria. It's particularly useful when you need to locate files based on their names, sizes, permissions, modification times, and more.
```
find  [path/to/directory]  [parameters]
```

## Find by Name:

- To Find all Files stored in the given path which has .jpg extension
```
find [path] -name '*.jpg'
```
- To Find all Files stored in the given path which has file name as "test" (CASE SENSITIVE)
```
find [path] -name test
```
- To Find all Files stored in the given path which has file name as "test" (CASE INSENSITIVE)
```
find [path] -iname test
```
- To Find all Files stored in the given path which starts with character 'h'
```
find [path] -name "h*"
```

## Find by Size:
| Notation | Meaning  |
| :------------: | :------------: |
|  c | bytes  |
|  k |  kilobytes |
|  M | megabytes  |
|  G | gigabytes  |

- To Find all Files stored in the given path which has size more than 10 MB
```
find [path] -size +10M
```
- To Find all Files stored in the given path which has size less than 10 MB
```
find [path] -size -10M
```
- To Find all Files stored in the given path which has size exactly 10 kB
```
find [path] -size 10k
```

## Multiple Find Filter:
- To Find all Files stored in the given path which has size exactly 10 kB **AND** Filename starts with 'h'
```
find [path] -size 10k -name "h*"
```
- To Find all Files stored in the given path which has size exactly 10 kB **OR** Filename starts with 'h'
```
find [path] -size 10k -o -name "h*"
```

## Find by Permissions:
- To Find all Files stored in the given path which has permissions exactly 745
```
find [path] -perm 745
```
- To Find all Files stored in the given path which has permissions atleast 745
```
find [path] -perm -745
```
- To Find all Files stored in the given path which has any permissions of 745
```
find [path] -perm /745
```
