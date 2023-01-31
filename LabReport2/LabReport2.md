# Lab Report 2

## Writing a Web Server

We were tasked with making a web server that tracks incoming parameters and prints them out for the user to see. In this server, the user would send their requests by appending `/add-message?s=<string> ` to the end of the http://localhost:# url. A screenshot of the code is pasted below; additionally, the entire code can be found at [this link]().

![Image](images/String_Server_Code.png)

To start the server, first compile the 2 java classes by typing `javac Server.java StringServer.java`; then, type `java StringServer 4000` to run the String Server class. As seen in the screenshot above, this runs `public static void main(String[] args)` method in the String Server class and accepts a number parameter, which will be the port where the server is hosted. In this example, because I inputted 4000 as a parameter, the server now runs on http://localhost:4000 . 

When you go to http://localhost:4000 , the Handler method will be called, and the `inputtedWords` & `stringOfInputtedWords` variables will be declared. Then, the `public String handleRequest(URI url)` method will be called, with the current URL ( http://localhost:4000 ) as the parameter. Then, the method checks if the path for current URL/parameter equals `/add-message`; however, since the path is currently `/`, the block in the if-statement is not executed, so "Hello. Please append /add-message?s=<String> to the end of the URL" is returned. This is demonstrated in the screenshot below. 
  
![Image](images/Pls_Append.png)
  




[this website]( https://code.visualstudio.com/docs/setup/mac )
