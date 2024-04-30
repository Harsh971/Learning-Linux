# AWK Comamnd in Linux

## Description

awk is a powerful programming language primarily used for text processing and data extraction in Linux and Unix environments. It operates on records (lines) and fields (words or columns) in a file, making it very effective for tasks like searching, filtering, modifying, and formatting text-based data.

1. **Basic Structure:**
```
awk 'pattern { action }' filename
```
- **pattern**: An optional condition that specifies when the action should be performed. If omitted, the action is performed on every input line.
- **{ action }**: The action to be performed on lines that match the pattern. If the pattern is omitted, the action is performed on every line.
- **filename**: The name of the file(s) to process. If omitted, awk reads from the standard input (usually piped input).

<hr>

2. **Fields and Records**:<br>By default, awk divides each input line into fields based on whitespace (spaces or tabs). You can access these fields using the variables $1, $2, $3, etc. For example, $1 represents the first field, $2 represents the second field, and so on. You can also access the entire line using the variable $0.

<hr>

3. **Actions**:
- **Print Action**: One of the most commonly used actions is the print action, which outputs text. For example, print $1 prints the first field, and print $0 prints the entire line.
- **Assignment**: awk allows you to assign values to variables. For example, total += $3 adds the value of the third field to the variable total.
- **Control Flow**: awk supports conditional statements (if, else, else if) and loops (while, for) for more complex processing.
- **Built-in Functions**: awk provides many built-in functions for string manipulation, arithmetic operations, and more. For example, tolower() converts a string to lowercase, and substr() extracts a substring from a string.

## Example 1 : Print Specific Fields
Suppose you have a file named data.txt with the following content :
```
Name    Age    City
Alice   30     New York
Bob     25     Los Angeles
Charlie 35     Chicago
```
You can use awk to print specific fields. For instance, to print only the names and ages:
```
awk '{ print $1, $2 }' data.txt
```
This command will output:
```
Name Age
Alice 30
Bob 25
Charlie 35
```

## Example 2 : Filter Lines Based on a Condition 
Let's say you want to filter lines where the age is greater than 30. You can do this with awk :
```
awk '$2 > 30' data.txt
```
This command will print only the lines where the age (the second field) is greater than 30 :
```
Charlie 35 Chicago
```

## Example 3: Calculate Total
Suppose you want to calculate the total age. You can use awk to sum up the ages in the third column :
```
awk '{ total += $2 } END { print "Total age:", total }' data.txt
```
This will output:
```
Total age: 90
```

## Example 4: Print Lines Matching a Pattern
Let's say you want to print lines containing the city "New York". You can use awk with a pattern match :
```
awk '/New York/' data.txt
```
This will print :
```
Alice 30 New York
```

## Example 5: Custom Formatting
You can also customize the output format. For instance, if you want to print the names and ages separated by a comma :
```
awk '{ print $1 "," $2 }' data.txt
```
This will output :
```
Name,Age
Alice,30
Bob,25
Charlie,35
```
