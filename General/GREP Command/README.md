# GREP Comamnd in Linux

## Description

**`grep`** stands for "Global Regular Expression Print". It's a powerful command-line utility used for searching text patterns within files or streams of text. grep is a versatile tool for extracting information from large sets of data based on specific search criteria.

### **Basic Structure:**
```
grep [options] pattern [filename]
```
- **pattern**: The regular expression or text pattern to search for.
- **filename**: The name of the file(s) to search. If omitted, grep searches standard input (piped input or keyboard input).

### Common Options:
Here are some common options used with grep:

- **`-i`** : Ignore case distinctions in both the pattern and input files.
- **`-v`** : Invert the match, i.e., select non-matching lines.
- **`-n`** : Print the line number with the output lines.
- **`-r`** or **`-R`** : Recursively search subdirectories.
- **`-l`** : Print only the names of files containing the pattern.
- **`-c`** : Print only a count of matching lines.
- **`-e pattern`** : Specify multiple patterns to search for.


## Example 1: Search for a Pattern in a File
Suppose you have a file named example.txt with the following content :
```
Hello, world!
This is a test file.
```
You can use grep to search for occurrences of the word "test" in example.txt:
```
grep "test" example.txt
```
This will output:
```
This is a test file.
```

## Example 2: Case-Insensitive Search
If you want to search for the word "test" regardless of case, you can use the -i option :
```
grep -i "test" example.txt
```
This will also match "Test" or "TEST".


## Example 3: Print Line Numbers
To print line numbers along with the matched lines, you can use the -n option :
```
grep -n "test" example.txt
```
This will output :
```
2 : This is a test file.
```
