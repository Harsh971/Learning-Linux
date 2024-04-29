# cut Command in Linux

## Description

The **`cut`** command in Linux is used to extract sections from each line of input data (usually text files) and print the result to standard output. It's particularly useful for processing delimited data, such as CSV files, tab-separated values, or any text data with fields separated by a specified delimiter

## Basic Structure :

```
cut [options] [file]
```

- **`[options]`**: Various options that modify the behavior of the **`cut`** command.
- **`[file]`**: Optional. Specifies the file from which to read input. If not specified, **`cut`** reads from standard input (stdin).

## Common Options :

- **d, --delimiter=DELIMITER**: Specifies the delimiter character that separates fields in the input. By default, the tab character is used as the delimiter.
- **f, --fields=LIST**: Specifies the list of fields to be extracted from each line of input. Fields are numbered starting from 1.
- **c, --characters=LIST**: Specifies the list of character positions to be extracted from each line of input.

## Examples:

1. Extracting Field 1 from space delimitered Data

```jsx
cut -d ' ' -f 1 test.txt
```
2. Extracting Field 2 from space delimitered Data and storing it into City.txt File

```jsx
cut -d ' ' -f 2 test.txt > City.txt
```
<img src="https://github.com/Harsh971/Learning-Linux/blob/main/General/cut%20Command/image1.png"><br><br>
## **Additional Tips:**

- **Multiple Fields or Characters**: You can specify multiple fields or character ranges separated by commas. For example, **`f1,3`** will extract the first and third fields.
- **Field Ranges**: You can specify a range of fields using a hyphen. For example, **`f1-3`** will extract fields 1 through 3.
