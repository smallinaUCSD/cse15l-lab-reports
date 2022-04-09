**Lap Report 1** 

In this lab report I will go over how to download, install and run VSCode, remotely connecting to UCSD's servers, basic terminal commands, moving files, setting an SSH key, and optimize remote running. 

**Step 1: Download VSCode**

Click the link below to download VSCode IDE respective to your machine (OS or Windows). The below steps are for Mac OS users. 

[VSCode link for download](https://code.visualstudio.com/download)

The VSCode should be in your **Downloads** folder. Once its done downloading double click to to open the application. 

*Sidenote: you can drag the VSCode Icon to your **Applications** folder to access it later.*

You should see a screen like this: 

 ![VSCode Open](VSCodeOpen.png)

**Step 2: Remotely Connect to UCSD's Server**

[Install SSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

For Mac OS users you can use the in built terminal on your device by pressing ⌘ + space and then typing in *terminal*. 

Should look like this:

![Terminal Mac](Terminal.png)

A small window should pop up like this: 

![Real Terminal](RTerminal.png)

Now type this command into your terminal to remotely connect to UCSD's server. 

**Command:** ssh cs15lsp22zz@ieng6.ucsd.edu

**Caution:** you should use your assigned email address and not the one from the example. 

[Click here to find your email address](https://students.ucsd.edu/campus-services/technology/computers/index.html)

Enter the password of your AD login when prompted. Now you should have access to the server. 

This is what your screen should present:

![Login Page](Login.png)

Then press ⌘ + D to exit the server.

**Step 3: Trying Some Commands**

Open up your terminal using ⌘ + space and then typing terminal in the search bar.

[Click the link to see different terminal commands](https://www.makeuseof.com/tag/mac-terminal-commands-cheat-sheet/)

Now in your terminal lets practice some commands.

Enter **ls** in your terminal like this:

![ls command](LsCommand.png)

ls command prints all the files and subdirectories of the current directory. 

Enter **pwd** in your terminal:

![pwd command1](PWD1.png)

pwd command prints your working directory. 

Enter **cd (name of file that was printed with the ls command)**.

![cd command](CD.png)

cd command changes your current directory to the new directory that you typed. **cd ..** command takes you up one directory, and **cd ~** takes you to the root directory. 

Then enter **pwd**. Your current location should have changed because you have entered a different directory. 

![pwd command2](PWD2.png)

Then enter **clear**.

![clear command](Clear1.png)
![clear command output](Clear.png)

clear command clears the terminal screen. 

**Step 4: Move/Copy Files with scp**

Open up your terminal using ⌘ + space and then typing terminal in the search bar. 

Type **vim (name of file).java**. Then click enter to create a new file. Type **i** on your keyboard. You should see insert at the bottom left corner. This means that you are currently editing the file that you created. 


Copy and Paste the code below: 
```java
    class WhereAmI {

        public static void main(String[] args) {

            System.out.println(System.getProperty("os.name"));
            System.out.println(System.getProperty("user.name"));
            System.out.println(System.getProperty("user.home"));
            System.out.println(System.getProperty("user.dir"));
        }

    }
```

![Vim](Vim.png) 

Then click the esc key. This means that your done editing your file. Then type the command **:wq** and enter to save and quit the file that you created. 

*Sidenote: Alternately, could use VSCode IDE to create, edit, save the java file, connect to the UCSD Server and perform remote operations.*

Then compile and run the java program that you made using the commands: 

Compile Java File: javac (filename)

Run Java File: java (filename)

![Compile](JavaC1.png) 

Once the java program compiled and ran. Enter this command: **scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/**

**Caution: remember to use the email assigned to you** 

Then you should enter your password. 

Now enter the ssh command to login into the sever and enter your password. Now use the command ls. The file that you created on your home directory should pop up in the UCSD server. Now you can compile and run your program using javac and java. 

![SCP](SCP.png) 

**Step 5: Setting up an SSH key** 

Type in the terminal command ssh-keygen. 

This should generate a public and private rsa key pair. Then enter the file that you want to save the key in. After that,  enter the passphrase that you want to use to protect that key. 

The terminal should then out put a random fingerprint/diagram. 

![keygen](Keygen.png)

Then log in to the UCSD server using your assigned email and password. Once you are connect use the terminal command **mkdir .ssh** to make a new directory .ssh. Logout of the server with control D.

![mkdir](mkdir.png)

Then type this **scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys** into the terminal. 

![loginwithoutpassword](LoginWithoutPassword.png)

*Sidenote: change the username and the filepath.* 

**Step 6: Optimize Remote Running** 

To run commands directly on the server you can use "" around the terminal command.

For example: 
**ssh cs15lsp22zz@ieng6.ucsd.edu "ls"** would log you into the server and run the command ls which would print out all the files and subdirectories. 

Additionally, having semicolons between commands allows mutiple commands to run at once.

For example: 
**cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI** would copy the file WhereAmI.java, compile it, and run the program. 

![Optimalizing Terminal Commands](OptimizingTerminal.png)

*Sidenote: pressing the up arrow key will allow to access previous terminal commands that you performed.*

**Conclusion**

This concludes lab report 1. In this lab report I documented the steps to download and run VS.Code, used vim editor for file operations, and used terminal to perform local and remote operations on UCSD server such as: basic terminal commands, move/copy files, generate and copy an SSH key, and perform remote operations optimally. 

Thanks for reading. 






