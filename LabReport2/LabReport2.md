# Lab Report 2

## Writing a Web Server

We were tasked with making a web server that tracks incoming parameters and prints them out for the user to see. In this server, the user would send their requests by appending `/add-message?s=<string> ` to the end of the http://localhost:# url. Here is the code for the string server:

![Image](images/String_Server_Code.png)

To start the server, first compile the 2 java classes by typing `javac Server.java StringServer.java`; then, to officially start the server, type `java StringServer 4000` to run the String Server class. As seen in the screenshot above, this runs `public static void main(String[] args)` method in the String Server class and accepts a number parameter, which will be the path where the server is hosted. In this example, because I inputted 4000 as a parameter, the server now runs on http://localhost:4000 . 




[this website]( https://code.visualstudio.com/docs/setup/mac )
