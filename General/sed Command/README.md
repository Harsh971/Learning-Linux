# sed Command in Linux

## Description

**sed (stream editor)** is a command-line utility that processes text line by line. It reads input text from files or standard input (stdin), applies specified text transformations or editing commands to each line, and then writes the result to standard output (stdout). It's commonly used for tasks such as search and replace, text filtering, and text transformations.
**sed** is a powerful and versatile tool for text processing and manipulation, making it invaluable for tasks ranging from simple text transformations to more complex editing operations. Its flexibility and ease of use make it a staple in the toolkit of many Linux users and system administrators.

## Basic Structure :

```
sed [options] 'command' [filename]
```
- **[options]:** Various options that modify the behavior of the sed command.
- **'command':** Specifies the editing command or script to be applied to the input.
- **[filename]:** Optional. Specifies the file to be processed. If not specified, sed reads from standard input.


## Examples:
1. Replace **first** occurrences of "Cty" with "City" in a file named test.txt:
```
sed  -i  's/Cty/City/'  test.txt

-i : Inplace, which means changes applied in sed is saved in the original source file
s/ : Substitution, used when we have to Substitute one string with other
```

<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/sed%20Command/image1.png"></img>

2. Replace **all** occurrences of "Cty" with "City" in a file named test.txt:
```
sed  -i  's/Cty/City/g'  test.txt
```
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/sed%20Command/image2.png"></img>

3. Delete all lines containing the word "error" in a log file:
```
sed  -i  '/error/d'  logfile.txt
```
4. Print only lines containing the word "important" in a file:
```
sed  -n  '/important/p'  data.txt
```


