# Lab Report 3 - Grep 

## What is Grep?

`Grep` is a linux command line argument that searches a file for a user-specified pattern and displays all lines that contain that pattern. This lab report will discuss 4 variations that can be paired with `grep` to produce many creative outputs. 

## 4 Grep Command Line Operations

> grep -r 

```
$ grep -r "Lucayans" written_2 > lucayans-result.txt

$ wc lucayans-result.txt
$ 2     260    1659 lucayans-result.txt
```
`Grep -r` recursively searches all files in a given folder and subfolders for how many lines contain the specified word. In the example above, the command searched written_2 and all its subfolders/directories to check which lines contained the word "Lucayans", and according to the output, only 2 lines in the entire written_2 directory contained the word Lucayans. 

We were tasked with making a web server that tracks incoming parameters and prints them out for the user to see. In this server, the user would send their requests by appending `/add-message?s=<string> ` to the end of the http://localhost:# url. A screenshot of the code is pasted below; additionally, the entire code can be found at [this link](https://github.com/SiyaKamboj/cse15l-lab-reports/tree/main/LabReport2).

![Image](images/String_Server_Code.png)
