# Lab Report 1

## Installing VSCode on my personal device

![Image](images/vscode_downloaded.png)

  Since VSCode was my IDE for CSE 11, I had already downloaded it on my macbook last quarter. However, for the purposes of this lab, I reinstalled it on my local device by following the instructions on [this website]( https://code.visualstudio.com/docs/setup/mac ). As per the first step, I clicked [this link]( https://go.microsoft.com/fwlink/?LinkID=534106 ) which automatically downloaded a zip file to my device's downloads folder. To open the zip file, I double clicked it in my downloads folder, which, then, installed the Visual Studio Code application in my Downloads folder, as shown below: 
  
![Image](images/VSCode_in_downloads_folder.png)

   Then, I dragged the Visual Studio Code Application to the Applications folder; however, since I already had Visual Studio Code in my applications folder, I was prompted to choose whether I want to keep both apps, replace, or stop the operation, and I chose to replace the current VSCode application. To confirm that the newly installed VSCode worked, I double clicked the app in the applications folder, and the following message popped up: 

![Image]( images/ensure_VSCode_safe.png )

   After selecting "yes", I was successfully able to open and run new and existing projects in VSCode. For all future projects, I was able to open VSCode without the pop, either through the applications folder or the finder on my macbook. Since I verified VSCode properly worked, I deleted the zip file from my Downloads folder, thereby removing unnecessary clutter. 

## Remotely Connecting to the computers in the CSE Building

  To remotely connect to the UCSD ieng6 server, I first found my course specific account for CSE15L at [this link]( https://sdacs.ucsd.edu/~icc/index.php ), which redirected me to a page where I inputted my UCSD username (sskamboj) and PID. Using this information, the website led me to the first page pictured below, informing me that my account username is cs15lwi23atq. When I selected the button with my username, I was allowed to change my password using the Global Password Reset tool. It should be noted that the second screenshot below is from the second time I reset my password, as I forgot to screenshot my first password reset during lab. For the "old password" field, I inputted the default password that was emailed to me, and inserted my own password for the new password.

![Image]( images/found_course_account.png )
*This is the first screenshot, where I found my course specific account.*

![Image]( images/change_password_tool.png )
*This is the second screenshot, where I was able to change my password for my CSE 15L Account.*
  
  After about 15 minutes, my password was successfully updated, so I tried to follow the [instructions]( https://ucsd-cse15l-w23.github.io/week/week1/#week-1-lab-report ) given in class. However, the rest of my lab group and I had issues setting our default terminals to use gitbash in VSCode. After about 5 minutes of difficulty, one of my group members (who also used a macbook) discovered that we could simply use the terminal on our macs instead of configuring the terminal in VSCode, since we are not using Windows. 
  
  After we solved the issue with the terminal, I was able to establish a connection with the UCSD ieng6 servers by typing `ssh cs15lwi23atq@ieng6.ucsd.edu`. When I first connected, I had to confirm that I received the following message on the terminal:
  `The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
   RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
   Are you sure you want to continue connecting (yes/no/[fingerprint])? `
  
  Since I wantted to continue connecting, I typed `yes` and was prompted to input my password; however, after that, I received the following message pictured below every time I connected, which did not prompt me to proceed with any further action, aside from typing in my password. 
  
![Image](images/terminal.png)

## Experimenting with Commands on the Terminal

![Image](images/running_commands.png)

Once I established a secure connection to the lab computers using the aforementioned steps, I ran through a series of commands to experiment with the connection, as shown in the photo above. For instance, when trying to access another group member’s files (using the ls /home/linux/ieng6/… command), I got the message “Permission denied,” likely to ensure that you cannot search through other students’ files without being logged in to their account. On the other hand, when I insert my own account (rather than a group members), it returns 2 things: hello.txt and perl5, showing that I have the permissions to access my own files through the remote server.
