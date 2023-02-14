# Lab Report 3 - Grep 

# What is Grep?

`Grep` is a linux command line argument that searches a file for a user-specified pattern and displays all lines that contain that pattern. This lab report will discuss 4 variations that can be paired with `grep` to produce many creative outputs. 

# 4 Grep Command Line Operations

## grep -r 

```
$ grep -r "Lucayans" written_2 > lucayans-result.txt

$ wc lucayans-result.txt
$ 2     260    1659 lucayans-result.txt
```
`grep -r` recursively searches all files in a given folder and subfolders for how many lines contain the specified word. In the example above, the command searched written_2 and all its subfolders/directories to check which lines contained the word "Lucayans", and according to the output, only 2 lines in the entire written_2 directory contained the word Lucayans. 

```
$ grep -r "dklgjkdfjg" written_2 > random-result.txt

$ wc random-result.txt
$ 0       0       0 random-result.txt
```
According to the output of the second example, no file in any of the subdirectories of written_2 contained a line with the word "dklgjkdfjg", which was expected. 
