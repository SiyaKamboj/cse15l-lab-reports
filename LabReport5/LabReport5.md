# Lab Report 5 - Report 4 Reflection

## What is Lab Report 4?
In Lab Report 4, we were tasked with learning how to navigate the command line quickly to make future programming tasks easier. Some of the tasks consisted of logging into the ieng6 server, cloning the testing repository, editing the failing tests, re-running the tests to ensure the edits are succesful, and, ultimately, commiting and pushing the change to my github account.

It should be noted that before working on the command line, I generated an ssh key for my ieng6 account, so that I did not have to type my password for every login attempt. I had also generated an ssh key for my github account, so that I could git clone and git push when I am logged into my ieng6 account on the commandline.

## Original Implementation of Lab Report 4
Here is a step-by-step implementation of lab report 4:
1. First, I typed `ssh cs15lwi23atq@ieng6.ucsd.edu` into the terminal. Because of my ssh key, I was not required to enter a password to log into my ieng6 account.
2. I entered `git clone git@github.com:SiyaKamboj/lab7.git`. This link is the ssh clone url from github.
3. Then, I changed the directory by typing `cd lab7/` to run the JUnit tests
4. To compile the tests, I typed `<Ctrl-R>` to search history and retrieve the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
5. To run the tests, I typed `<Ctrl-R>` to search history and retrieve the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
6. Then, I edited the ListExamples file using the `nano` command 
7. Now, I used the `<up arrow>` keys to re-receive the javac and java commands from step 4 and 5 respectively in order to re-run the tests and demonstrate that it works. 
8. Finally, I git added the changed file (ListExamples.java), git committed, and git pushed to my own forked copy of the repository.

Detailed information and images about my implementation of lab report 4 can be found in [my previous lab report](https://siyakamboj.github.io/cse15l-lab-reports/LapReport4/LabReport4.html).

## Alternative Way of Implementing Lab Report 4
The task we were assigned was navigating the command line quickly. In class, we had learned about bash scripts, a file that contains a series of commands. Therefore, if a bash script was used, ___
