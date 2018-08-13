# Command

## Useful command
Nearly all command use the format like that "[COMMAND]...[OPTION]...[FILENAME]"

Here is a list of command :


**ls**: list the list of directory

    -l: use a long listing format
    -a: show all files(incloud hidden files)
So you can run like that ``ls -al`` to  show all the directory and file with no hide in list.

| Command  | Description |
| :---     | :---        |
| cd       | switch the dir to target directory |
| mkdir    | creat a new directory |
|pushd     |switch the dir to target directory and push current dir into the directory stack.If path is omitted, it will print the directoy stack.|
|popd      |pop the dir from the top of the directory stack and switch to target|
| cat      | show what writed in file |
| mv       | move file to somewhere `mv [file name] [where]` |
| rm       | delete file `-r: delete directory` |
| ls       | list the list of directory |


## How to login other computer

### Introduction to SSH

For this page, I will introduce some basic skills about usage of _ssh_ command.And I will show you how to login into our personal lab computer from dormitory.

### What's SSH

> The ssh command provides a secure encrypted connection between two hosts over an insecure network. This connection can also be used for terminal access, file transfers, and for tunneling other applications.

For us, it's just a tool for login **Linux**. you can use your Windows login Linux. 

### How to use SSH command login other Linux

Firstly, Run the next command to sure the ssh server is installed in your Linux.

`sudo apt-get install openssh-server`

And if we want to log into a server through _**ssh**_, we should have an **account**, **password** and server's **ip** or **domain name**.

```
ssh [username]@hostname [command]
```

Without the username, the default username is the account of your personal Linux computer.

If this is the first time you use _ssh_ to connect to this remote machine, you will see a message as below:

```bash
The authenticity of host '[SERVER NAME]' cannot be established.DSA key fingerprint is 04:48:84:31:b0:z0:5a:9b:01:9d:b3:a7:47:e2:b1:0c.Are you sure you want to continue connecting (yes/no)?
```

Type ``yes`` to continue. This will add the server to your list of known hosts (Stored in `~/.ssh/known_hosts`) as seen in the following message. So we cannot type 'yes' again when we log into **Linux** next time.

For why we get message like before, you can get answer from [this blog](https://www.ssh.com/attack/man-in-the-middle) Simply speaking, it's because man-in-the-middle attack. 

After you get the key for the first time, move it to `~/.ssh/` directory with:

```
mv /path/to/key ~/.ssh
```

And then change the permissions of the **key** to 600 with command below:

```
chmod 600 ~/.ssh/key
```

For more knowledge about permission control, please refer to [blog](https://www.digitalocean.com/community/tutorials/an-introduction-to-linux-permissions). 

When we have done all of this before, we can log into the server with **key**:

```
ssh -i ~/.ssh/key [USERNAME]@[SERVER ADRESS]
```

In fact, we don't need to use key to log into **Linux**, the one need to log with key is make sure the safe computer.

Besides this basic knowledge about _ssh_, the usage of _scp_: a tool for file transfer based on _ssh_ is important for us too. The next chapter will talk about this commad.

### Use ssh show GUI on other Linux

```
ssh -X [USERNAME]@[SERVER ADDRESS]
```
And you can run the GUI program in terminal like `gedit`. The GUI will show on your screen.

### Use SSH login your Linux on Windows

> Maybe you don't know about that the SSH had installed in lasted Windows 10, you can use it in `powershell` or `cmd`.And if your Windows system is other version，you can install [Xshell](https://www.netsarang.com/products/xsh_overview.html) or other ssh client in your system.

Terminal Emulator can do a favor when we need to access on your PCs. Here, we take _**Xshell**_ as an example.

#### How to use Xshell:
The operation in Xshell is almost the same as that in the shell of linux system. The only difference is that a new window will pop up in Xshell, where the account password has to be input.

If you want get your username be remembered in Xshell or don't enter the password to login your Linux system. Just follow the step to setup your Xshell.

**Step 1** 

Click the button to add a new configfile.

**Step 2**

Set the config to suitable for your Linux.

If your don't know your computer IP address please use the `ifconfig` command in your Linux to show the IP address.

**Step 3**

If you have a Private key to login your Linux just change the method.

**Step 4**

Click the OK button to save the config file, and connect it.

The Xshell will recheck the key,you should reviewer the message.

After all, you will use SSH login in your Linux. 

### Use SSH Show GUI on Windows

You can use Xmanager to show GUI on your Windows.

download [Xmanager](https://www.netsarang.com/products/xmg_overview.html)

**Expand**

If you want, you also could install WSL(Windows Subsystem for Linux) on your Windows 10. WSL will give a Linux virtual environment on Windows 10.

Here is a official doc about it: https://docs.microsoft.com/en-us/windows/wsl/install-win10

## How to transfer file to other Linux use command

### An Introduction of SCP

_**scp**_ is a tool for transfer files between server and local computer through *ssh* protcol. It's a very useful tool for linux user. Well, for windows user, you can use [Xshell](https://www.netsarang.com/products/xsh_overview.html) and [Xftp](https://www.netsarang.com/products/xfp_overview.html) instead.
