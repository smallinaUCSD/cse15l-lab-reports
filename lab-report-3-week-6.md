# Lab Report 3

In this lab report I will go over streamlining ssh configuration, setting Github access from ieng6, and copying whole difrectories with scp -r command. 

# Task 1: Streamlining ssh Configuration 

![Open SSH Config](OpenConfig.png)

This is how I accessed the config file in VSCode.

![SSH Configuration](sshConfigFile.png) 

This is the config file that I used and I edited it on VSCode. 

![SSH Command Login](sshcommandlogin.png)

The command that I used which streamlined my login to the ieng6 server was ssh ieng6. 

![SSH SCP](SCPFilecpoy.png)

This is the command that I used to copy the file MarkdownParse.java using the alias ieng6 specificed in the ssh config file. 

# Task 2: Setup Github Access from ieng6 

First I checked for ssh public and private keys on my local machine that were generated using ssh keygen. The private key and public keys are stored in the ~/.ssh folder as shown below.

![SSH Key on Local](SSHKey.png)

Registered public key on github. Go to settings and click ssh and gpg keys. Then I clicked add new ssh key.
![GitHub SSH Key](GitHubSSHKey.png)

Copied and pasted my public ssh key and saved it to Github.
![SSH Key](SSHKeyGitHub.png)

I copied the ssh keys from my local machine to the server ieng6 and modified the ssh config file to add the git server information.

![SSH Config Update](GitSSHConfig.png)

Edited MarkdownParse.java file. Used git commands to push the change onto github.

![Git Commands](GitCommands.png) 

I generated a personal access token as a password is no longer accepted. 

![Success Push](GitPush.png)

[Link for resulting commit](https://github.com/smallinaUCSD/markdown-parser/commits/main)

# Task 3: Copy whole directories with scp -r

I copied the directory markdown-parser with the recursive scp command: 

```
scp -r /Users/smallina/Documents/GitHub/markdown-parser ieng6:~/markdown-parser
```

![Copied Folder](SCPCopyMPD.png)

I compiled and ran the java file on the server.  

![Compile and Ran Test](RunningMCF.png)

To copy folder, compile, and run on the server using a single line command: 

```
scp -r /Users/smallina/Documents/GitHub/markdown-parser ieng6:~/markdown-parser; ssh ieng6 cd markdown-parser; javac MarkdownParse.java; java MarkdownParse Test1.md
```

![Single Line](SingleLine.png)
![Compile and Run](Compileandrunsingleline.png)

# Conclusion

In this lab report I went over streamlining ssh configuration, setting Github access from ieng6, and copying whole directories with scp -r command and a combine command with scp -r and ssh to copy whole directory, compile and run the java file. Thanks for reading.