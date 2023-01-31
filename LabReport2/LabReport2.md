# Lab Report 2

## Writing a Web Server

We were tasked with making a web server that tracks incoming parameters and prints them out for the user to see. In this server, the user would send their requests by appending `/add-message?s=<string> ` to the end of the http://localhost:# url. A screenshot of the code is pasted below; additionally, the entire code can be found at [this link](https://github.com/SiyaKamboj/cse15l-lab-reports/tree/main/LabReport2).

![Image](images/String_Server_Code.png)

To start the server, first compile the 2 java classes by typing `javac Server.java StringServer.java`; then, type `java StringServer 4000` to run the String Server class. As seen in the screenshot above, this runs `public static void main(String[] args)` method in the String Server class and accepts a number parameter, which will be the port where the server is hosted. In this example, because I inputted 4000 as a parameter, the server now runs on http://localhost:4000 . 

When you go to http://localhost:4000 , the Handler method will be called, and the `inputtedWords` & `stringOfInputtedWords` variables will be declared. Then, the `public String handleRequest(URI url)` method will be called, with the current URL ( http://localhost:4000 ) as the parameter. Then, the method checks if the path for current URL/parameter equals `/add-message`; however, since the path is currently `/`, the block in the if-statement is not executed, so "Hello. Please append /add-message?s=<String> to the end of the URL" is returned. This is demonstrated in the screenshot below. 
  
![Image](images/Pls_Append.png)
  
If you go to http://localhost:4000/add-message?s=Hi, the Handler method will again be called, and the `inputtedWords` & `stringOfInputtedWords` variables will be re-declared. Then, the `public String handleRequest(URI url)` method will be called again, with the current URL ( http://localhost:4000/add-message?s=Hi ) as the parameter. Then, the method checks if the path for current URL/parameter equals `/add-message`; since it does, the code then splits the query at the equals sign. In this case, because the character before the equals sign is 0, it is saved into `params[0]`, and "Hi" is saved into `params[1]` since it immediately follows the `s=`. Because the first parameter is "s", the "Hi" is appened to the end of the empty ArrayList `inputtedWords`. Then, the content(s) from `inputtedWords` are concatenated into the `stringOfInputtedWords` String, which separates each indivual element with a new line. Ultimately, this string, which contains all the inputtedWords (in this case, only "Hi" has been inputted), is returned and displayed on the webpage, as shown below.
  
![Image](images/Hi.png)
  
Afterwards, if you then go to  http://localhost:4000/add-message?s=How Are You , the process mentioned above repeats, except `params[1]` contains "How Are You" instead of "Hi". Hence, "How Are You" is appended to the end of `inputtedWords` ArrayList, which already contained "Hi". Hence, the following is outputted: 
  
![Image](images/Hi_How_Are_You.png)
  
---
  
## The Bug In the "reversed" Method
> Failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
> An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
> The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
> The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
