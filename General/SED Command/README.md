# SED Comamnd in Linux

## Description

**`sed`**, short for **"stream editor"** is a powerful command-line utility for filtering and transforming text. It's especially useful for performing non-interactive text transformations on input streams or files. sed processes text one line at a time, allowing you to apply a variety of editing commands to each line.

**Basic Structure:**
```
sed options 'commands' filename
```
- **options**: Optional flags that modify sed's behavior, such as -i for in-place editing.
- **'commands'**: A sequence of editing commands enclosed in single quotes.
- **filename**: The name of the file(s) to process. If omitted, sed reads from the standard input.

## Example 1: Substitute Text
Suppose you have a file named file.txt with the following content :
```
Hello, World12!
This is a test.
```
You can use sed to substitute occurrences of a word or pattern :
```
sed 's/test/example/' file.txt
```
This command will substitute the word "test" with "example" in the file :
```
Hello, World12!
This is a example.
```

## Example 2: Delete Lines Containing a Pattern
Suppose you want to remove lines containing the word "test" from file.txt:
```
sed '/test/d' file.txt
```
This command will delete lines containing the word "test" :
```
Hello, World12!
```

## Example 3: Insert Text Before a Line
Let's say you want to insert a new line before the first line of file.txt :
```
sed '1i\
This is the first line' file.txt
```
This command will insert "This is the first line" before the first line :
```
This is the first line
Hello, World12!
This is a test.
```

## Example 4: Append Text After a Line
Suppose you want to append a line after the last line of file.txt :
```
sed '$a\
This is the last line' file.txt
```
This command will append "This is the last line" after the last line :
```
Hello, World12!
This is a test.
This is the last line
```

## Example 5: Print Specific Lines
Let's say you want to print lines 2 to 4 of file.txt :
```
sed -n '2,4p' file.txt
```
This command will print lines 2 to 4 :
```
This is a test.
```

## Example 6: Using Regular Expressions
Suppose you want to replace all occurrences of digits with "X" in file.txt :
```
sed 's/[0-9]/X/g' file.txt
```
This command will replace all digits with "X" :
```
Hello, WorldXX!
This is a test.
```
