
# Week One Lab Report
**Alex Oshima**  
**PID: A1695817**

## How to log into a course-specific account on ieng6

### 1) **Installing VScode**
For this course we will be using VScode so lets first download it. - [VSCode Download](https://code.visualstudio.com/download)


![Image](Images/Lab-1/VSCode.png)



### 2) **Remotely Connecting**
First you will need your sources specific account login - [Find it here](https://sdacs.ucsd.edu/~icc/index.php)

![Image](Images/Lab-1/AccountLookup.png)

Next you should open up the terminal in VScode  

Now youre going to connect to ieng6 using the following command 
(Changing the zz to your unique account)

```
    ssh cs15lwi22zz@ieng6.ucsd.edu  
```

Next you'll have to enter your password 

![Image](Images/Lab-1/Login.png)


### 3) **Run Some Commands**

Try inputing some of the following commands into the terminal
```
* cd ~
* cd
* ls -lat
* ls -a
```

**EX**  

![Image](Images/Lab-1/ls-a.png)

### 4) **Moving Files with scp**
Next you'll practice transfering your files from the local machine to the remote machine

*Remember to log out of the remote machine with crtl + d*

Now from your local machine use the following command to send a file of your chosing
```
    scp fileName.fileExtension cs15lwi22zz@ieng6.ucsd.edu:~/
```

![Image](Images/Lab-1/scp.png)
The ~/ sends the file to the default directory on the recieving machine

### 5) **Setting an SSH Key**
SSH keys remove the requirment to enter your password everytime you want to ssh into a specific remote server

A public and private key pair is created and the remote server is given the public key

* First you must set up the ssh key on your local machine
![Image](Images/Lab-1/SSHkey.png)

* Next you will scp the public key from where you saved it on your local machine to the remote machine
```
    scp **Where ever you saved the public key** cs15lwi22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys
```

### **Optimizing Remote Running**
To optimize your experience you can use some short cuts
```
    ssh cs15lwi22zz@ieng6.ucsd.edu "ls"
```

That will login you in then run whatever command is in " " then log out
![Image](Images/Lab-1/SSHQ.png)

You can also run multple commands on one line by seperating them with semi colons
```
    ssh cs15lwi22zz@ieng6.ucsd.edu "ls"; javac WhereAmI.java; java WhereAmI
```
![Image](Images/Lab-1/Multiple.png)

While editing a local file then compling it and uploading it on a remote device may seem like it takes a lot of commands it can actually be done in just 2 keystrokes. After you type it the frist time (or copy and paste) you can upload the changes you made, compile and run them but just recalling your last command in the terminal with the up arrow and then hitting enter

```
scp WhereAmI.java  cs15lwi22aoj@ieng6.ucsd.edu:~/; ssh cs15lwi22aoj@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"
```
![Image](Images/Lab-1/CompressedCommandLine.png)

