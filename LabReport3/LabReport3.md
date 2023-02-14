# Lab Report 3 - Grep 

# What is Grep?

`Grep` is a linux command line argument that searches a file for a user-specified pattern and displays all lines that contain that pattern. This lab report will discuss 4 variations that can be paired with `grep` to produce many creative outputs, which can also be used in conjunction with each other

# 4 Grep Command Line Operations

## grep -r 

```
$ grep -r "Lucayans" written_2 > lucayans-result.txt
$
$ wc lucayans-result.txt
$ 2     260    1659 lucayans-result.txt
```
`grep -r` recursively searches all files in a given folder and its subfolders for how many lines contain the specified word. In the example above, the command searched written_2 and all its subfolders/directories to check which lines contained the word "Lucayans", and according to the output, only 2 lines in the entire written_2 directory contained the word Lucayans. This command is useful for finding necessary phrases or words in a disorganized folder/document structure. 

```
$ grep -r "dklgjkdfjg" written_2 > random-result.txt
$
$ wc random-result.txt
$ 0       0       0 random-result.txt
```
According to the output of the second example, no file in any of the files or subdirectories of written_2 contained a line with the word "dklgjkdfjg", which was expected. 

I discovered information about this command from lecture; however, I answered my clarifying questions using [this link](https://stackoverflow.com/questions/1987926/how-do-i-recursively-grep-all-directories-and-subdirectories). 

## grep -l

`grep -l` searches for the file(s) in which a given string or expression appears. If used in conjunction with `grep -r`, you can recursively search all subdirectories for the specific file that contains the given string or expression. This command can be helpful to find the number of files that contain a given string, in order to determine which files are repetitive and can, subsequently, get deleted. The examples below demonstrate the outputs for a series of examples: 

```
$ grep -l "vista" written_2/travel_guides/berlitz1/*.txt > files-vista.txt
$
$ cat files-vista.txt
$ written_2/travel_guides/berlitz1/IntroDublin.txt
$ written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
$ written_2/travel_guides/berlitz1/IntroMadeira.txt
$ written_2/travel_guides/berlitz1/WhereToFrance.txt
$ written_2/travel_guides/berlitz1/WhereToGreek.txt
$ written_2/travel_guides/berlitz1/WhereToIbiza.txt
$ written_2/travel_guides/berlitz1/WhereToIsrael.txt
$ written_2/travel_guides/berlitz1/WhereToJerusalem.txt
$ written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
$ written_2/travel_guides/berlitz1/WhereToMadeira.txt
```
In this example, I searched for the text files in the written_2/travel_guides/berlitz1/ directory that contain the string "vista" and saved the output in files-vista.txt. When opening files-vista.txt, the command line outputs the paths of the files that contain "vista" in the specified directory. 

```
$ grep -rl "vista" written_2 > files-vista.txt
$
$ cat files-vista.txt
$ written_2/travel_guides/berlitz1/IntroDublin.txt
$ written_2/travel_guides/berlitz1/IntroMadeira.txt
$ written_2/travel_guides/berlitz1/WhereToGreek.txt
$ written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
$ written_2/travel_guides/berlitz1/WhereToIsrael.txt
$ written_2/travel_guides/berlitz1/WhereToFrance.txt
$ written_2/travel_guides/berlitz1/WhereToMadeira.txt
$ written_2/travel_guides/berlitz1/WhereToIbiza.txt
$ written_2/travel_guides/berlitz1/WhereToJerusalem.txt
$ written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
$ written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
$ written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
$ written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
$ written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
$ written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
$ written_2/travel_guides/berlitz2/China-WhereToGo.txt
$ written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
$ written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
$ written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
$ written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
In this example, I used both `grep -r` and `grep -l` to recursively search through all the files and subdirectories in written_2 for the text files that contain the string "vista" and replace the contents of "files-vista.txt" with the output. When opening the new file, it is evident that more files (that are not in written_2/travel_guides/berlitz1/) contain the word "vista". 

I first learned about grep -l from the extension questions after the week 4 lab, using a variety of different internet resources such as [stackoverflow](https://stackoverflow.com/) and [geeksforgeeks](https://www.geeksforgeeks.org/).

## grep -v

`grep -v` was a command that I discovered at [this link](https://www.redhat.com/sysadmin/find-text-files-using-grep). It is a command that "inverts" grep by searching for the file that does NOT contain the user-specified pattern/word. This would be useful for mass-deleting all files that contain a word/phrase that is no longer necessary. 

```
$ grep -vl "jgfdjgjfgk" written_2/travel_guides/berlitz1/*.txt > random.txt
$
$ wc random.txt
$ 101     101    5147 random.txt
```
In the example above, I used grep -vl to determine the text files in the "written_2/travel_guides/berlitz1/" subdirectory that do not contain the word "jgfdjgjfgk." Since none of the text files contain the aforementioned word, all 101 files were returned by the output. 

```
$ wc written_2/travel_guides/berlitz2/Bahamas-History.txt
$ 43    2678   16802 written_2/travel_guides/berlitz2/Bahamas-History.txt
$
$ grep -v "Lucayans" written_2/travel_guides/berlitz2/Bahamas-History.txt > lucayans-new.txt
$ wc lucayans-new.txt
$ 41    2418   15249 lucayans-new.txt
```
From the first example for `grep -r`, we know that exactly 2 lines in Bahamas-History.txt contain the word "Lucayans." From the `wc` command at the beginning of this command, it is apparent that there are exactly 43 lines in the Bahamas-History.txt file. Therefore, it is implied that exactly 41 lines do not have "Lucayans," which is verified by the final `grep -v` command in the example above. 

## grep -m
`grep -m` was a command I found after typing `man grep` into the terminal. 
`grep -m` stops reading the file after it finds x number of lines that contain the given expression. It can be helpful if the user wants to check if a file contains a given string, but has a specific runtime that the program needs to fit under. 

```
$ grep -m 1 "Lucayans" written_2/travel_guides/berlitz2/Bahamas-History.txt > lucayans-new.txt
$
$ wc lucayans-new.txt
$ 1     134     809 lucayans-new.txt
```
From previous examples, it is known that there are exactly 2 lines in Bahamas-History.txt that contain the word "Lucayans"; however, in this example, the file stops gettng read after the first line contains the given expression. Hence, only 1 line contains "Lucayans" in this example. 




