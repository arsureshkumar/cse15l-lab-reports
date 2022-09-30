# Remote Tutorial
---
## Installing VSCode

Start by going to [this link](https://code.visualstudio.com/download) and downloading Visual Studio Code.

![image0](lab1-0.png)

Follow the installation instructions. Once the installation is complete, you should be looking at an image like this:

![image1](lab1-1.png)

*No screenshots of VSCode installation process (completed before lab)*

## Remote Connection

Go to [UCSD password reset](https://sdacs.ucsd.edu/~icc/index.php).

Enter username and ID number to find account.
Click "Reset Password" and follow the instructions thereafter. Make sure that the options to reset passwords for temporary accounts are also selected.

![image2](lab1-2.png)

Wait 10-15 minutes for the password change to take effect. In the meantime, go to [this link](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) and follow the instructions to install OpenSSH. Make sure to install just the client version, not the server version.

Once the password change has taken effect, go to Terminal -> New Terminal in VSCode.

In the new terminal, run `ssh cs15lfa22zz@ieng6.ucsd.edu`, replacing `cs15lfa22zz` with your own specific account name, then enter you password.
Select yes for any trust-related message, and you should now be able to run commands on the UCSD server.

![image3](lab1-3.png)

*No screenshots of OpenSSH installation process (completed before lab)*

## Commands

You can now try some commands on the UCSD server, such as mkdir, pwd, cd, ls, etc:

![image4](lab1-4.png)

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

![image5](lab1-5.png)

Now, you can use `scp` to copy the file over to the server, using the following command: `scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/`
After logging into the UCSD server again, WhereAmI.java should be visible, compilable, and runnable using terminal commands.

![image6](lab1-6.png)

## Keys
## Optimization
