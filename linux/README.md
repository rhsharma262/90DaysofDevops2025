Linux Administration Basics
This repository is a beginner-friendly guide to Linux administration. It covers essential topics like file permissions, package management, basic shell scripting, and Linux volumes. Let's get started!

Table of Contents
File Permissions

Package Management

Basic Shell Scripting

Linux Volumes

File Permissions
In Linux, every file and directory has permissions that control who can read, write, or execute them. Permissions are divided into three categories:

Owner: The user who owns the file.

Group: Users who are part of a group.

Others: Everyone else.

Viewing Permissions
Use the ls -l command to view file permissions:

bash
Copy
ls -l filename
Example output:

Copy
-rw-r--r-- 1 user group 0 Oct 10 12:34 filename
-rw-r--r--: Permissions (read, write, execute for owner, group, and others).

user: Owner of the file.

group: Group associated with the file.

Changing Permissions
Use the chmod command to change permissions:

bash
Copy
chmod 755 filename  # Gives read, write, execute to owner, and read/execute to group/others.
Package Management
Linux uses package managers to install, update, and remove software. Common package managers include:

APT (Debian/Ubuntu)

YUM/DNF (CentOS/RHEL/Fedora)

Installing a Package
bash
Copy
sudo apt install package_name  # For Debian/Ubuntu
sudo yum install package_name  # For CentOS/RHEL
Updating Packages
bash
Copy
sudo apt update && sudo apt upgrade  # For Debian/Ubuntu
sudo yum update  # For CentOS/RHEL
Removing a Package
bash
Copy
sudo apt remove package_name  # For Debian/Ubuntu
sudo yum remove package_name  # For CentOS/RHEL
Basic Shell Scripting
Shell scripting allows you to automate tasks in Linux. A shell script is a text file containing a series of commands.

Example Script
Create a file called hello.sh:

bash
Copy
#!/bin/bash
# This is a comment
echo "Hello, World!"
Make the Script Executable
bash
Copy
chmod +x hello.sh
Run the Script
bash
Copy
./hello.sh
Output:

Copy
Hello, World!
Linux Volumes
Linux volumes are used to manage storage. Common tasks include creating, mounting, and resizing partitions.

Listing Disks and Partitions
Use the lsblk command:

bash
Copy
lsblk
Mounting a Volume
Create a directory for the mount point:

bash
Copy
sudo mkdir /mnt/mydisk
Mount the volume:

bash
Copy
sudo mount /dev/sdb1 /mnt/mydisk
Unmounting a Volume
bash
Copy
sudo umount /mnt/mydisk
