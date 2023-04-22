# Lab Report 1
## Installing VSCode

To download Visual Studio Code, go to the website [Download VS Code](https://code.visualstudio.com/). There are different versions for Windows and Macs. This is what your screen should look like after opening VS Code. (It's ok if the recent field is empty on your screen. Since I used VS code before it automatically shows up the file I opened recently.)


![Image](Screenshot1.png)



## Remotely Connecting
The next step is to install git at [Download git](https://gitforwindows.org/) 

Open a new terminal in VS Code. Go to this post to see how to change your default terminal[Using bash on windows](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994)

Then, type in **$ ssh accountName@ieng6.ucsd.edu**, replace "accountName" with your acount that starts with "cse15l." Type in "yes" if the question "Are you sure you want to continue connecting" pops up. Finally, enter the password you created for your account to complete login.

Your terminal should look similar to the picture below after logged in.


![Image](Screenshot2.png)




## Trying Some Commands
Congratulations! Now you have successfully connected to a computer in CSE Department. From now on, whatever commands you type in will run on the computers at the basement of CSE building. It's the time to try out some commands to see what you will get. For Example:
* cd ~
Output: 
* pwd
Output:
/home/linux/ieng6/cs15lsp23/cs15lsp23au
* ls
Output: cs15l2  cse15lab2  perl5
* ls -lat
-rw-r--r--   1 cs15lsp23au ieng6_cs15lsp23  1005 Apr 22 15:05 .modulesbegenv
-rw-------   1 cs15lsp23au ieng6_cs15lsp23   584 Apr 14 22:09 .bash_history
drwxr-s---  10 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:29 .
drwx--S---   2 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:14 .ssh
drwxr-sr-x   3 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:13 .cache
drwxr-sr-x   2 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:13 perl5
drwxr-sr-x   3 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:13 .local
drwxr-sr-x   3 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:13 .config
drwxr-s---   3 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:04 cs15l2
drwxr-S---   3 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 21:01 .pki
drwxr-s---   3 cs15lsp23au ieng6_cs15lsp23  4096 Apr 14 20:59 cse15lab2
drwxr-sr-x 509 cs15lsp23   ieng6_cs15lsp23 40960 Apr 13 01:17 ..
* ls -a
.  ..  .bash_history  .cache  .config  .local  .modulesbegenv  .pki  .ssh  cs15l2  cse15lab2  perl5
-bash-4.2$ 
And the results you get should also look similar to the screenshot below:


![Image](Screenshot3.png)
