# Connect to a remote computer using SSH protocol

## What is ssh?

SSH (Secure Shell) is a cryptograpic network protocol used to securely operate network services over unsecured networks.

It allows users to:

* Remotely log in to another computer using the command line
* Execute commands on a remote machine
* Transfer files securely between computers

SSH uses TCP port 22 by default.

SSH replaced older unencrypted remote access protocols such as Telnet, which transmitted data (including passwords) in plain text.

## Install SSH on Ubuntu 20.04
Run
```Bash
sudo apt update
```
Example output:
![alt text](image.png)

Run
```Bash
sudo apt install ssh
```
Example output:
![alt text](image-1.png)
## Check SSH version
To verify SSH installation:
```Bash
ssh -V
```
Example output:
![alt text](image-2.png)
## Connect from Window to Linux Using SSH

1. **Get Linux IP Address and Username**

    Before connecting, you need:
    
    * Linux IP address
    * Linux username



**Check IP Address**

On Linux terminal:
```Bash
hostname -I
```
Example ouput
![alt text](image-3.png)

**Check Username**
```Bash
whoami
```
Example ouput
![alt text](image-4.png)

2. **Connect Linux Server**
SSH syntax:
```Bash
ssh username@server_ip
```
Example:
```Bash
ssh linux@192.168.1.101
```
Explanation:

* ssh --> start SSH client.
* linux --> Linux username. 
* 192.168.1.101 --> Linux server IP address.

After login successfully, your Windows CMD will become a Linux terminal session. 

Example:

![alt text](image-6.png)

**Test SSH Remote Command**
Create a folder from Windows CMD on the Linux machine.

Run:
```Bash
mikdir testWindow
```
![](image-7.png)

**Verify Folder on Linux Server**
Go back to Linux and check:
```Bash
ls
```
You should see:

*testWindow*

Example:

![alt text](image-8.png)

## Copy folder from Windows to Linux

Using **scp**

Example:I want copy file **iot_kit-0.0.1-SNAPSHOT.jar**  to **/home/linux/Documents/iot**
```Bash
scp -r iot_kit-0.0.1-SNAPSHOT.jar linux@192.168.1.100:/home/linux/Documents/iot
```
Open CMD **Window**:
<img width="1064" height="98" alt="image" src="https://github.com/user-attachments/assets/59b0421a-b675-492f-8c53-00e101989559" />
Verify on **Linux**:
<img width="315" height="48" alt="image" src="https://github.com/user-attachments/assets/917adfe1-834f-4fd7-80e6-368b106e5ea5" />

