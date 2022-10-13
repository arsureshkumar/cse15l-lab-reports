# Remote Tutorial
---
## Installing VSCode

Start by going to [this link](https://code.visualstudio.com/download) and downloading Visual Studio Code.

![image0](week1pictures/0.png)

Follow the installation instructions. Once the installation is complete, you should be looking at an image like this:

![image1](week1pictures/1.png)

*No screenshots of VSCode installation process (completed before lab)*

## Remote Connection

Go to [UCSD password reset](https://sdacs.ucsd.edu/~icc/index.php).

Enter username and ID number to find account.
Click "Reset Password" and follow the instructions thereafter. Make sure that the options to reset passwords for temporary accounts are also selected.

![image2](week1pictures/2.png)

Wait 10-15 minutes for the password change to take effect. In the meantime, go to [this link](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) and follow the instructions to install OpenSSH. Make sure to install just the client version, not the server version.

Once the password change has taken effect, go to Terminal -> New Terminal in VSCode.

In the new terminal, run `ssh cs15lfa22zz@ieng6.ucsd.edu`, replacing `cs15lfa22zz` with your own specific account name, then enter you password.
Select yes for any trust-related message, and you should now be able to run commands on the UCSD server.

![image3](week1pictures/3.png)

*No screenshots of OpenSSH installation process (completed before lab)*

## Commands

You can now try some commands on the UCSD server, such as mkdir, pwd, cd, ls, etc:

![image4](week1pictures/4.png)

Use `exit` to end the ssh session.

## SCP

On your own computer, create a java file called WhereAmI.java with this code:

```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

![image5](week1pictures/5.png)

Now, you can use `scp` to copy the file over to the server, using the following command: `scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/`
After logging into the UCSD server again, WhereAmI.java should be visible, compilable, and runnable using terminal commands.

![image6](week1pictures/6.png)

## Keys

To login to ssh servers without a password, a key must be generated and stored on the client and server computers.
Use the command `ssh-keygen` and do not set a passphrase. Use the default key storage location by using the enter key.

![image7](week1pictures/7.png)

Next, ssh into the server and make a directory called .ssh: `mkdir .ssh`. Use scp to copy the generated key file into the .ssh directory on the server.
Now, logging into the server should look like this:

![image8](week1pictures/8.png)

## Optimization

Using semicolons between commands allows multiple commands on the same line. Using a script file to condense multiple files allows for less keystokes when performing repeated actions.

![image9](week1pictures/9.png)
