# Linux Administration Guide

## Table of Contents
- [File Permissions](#file-permissions)
- [Package Management](#package-management)
- [Shell Scripting](#shell-scripting)
- [Linux LVM Volumes](#linux-lvm-volumes)

---

## File Permissions
Linux file permissions determine who can read, write, or execute a file.

### Permission Types:
- `r` (read) - View file contents
- `w` (write) - Modify file contents
- `x` (execute) - Run the file as a program

### Changing Permissions:
Use `chmod` to change permissions.
```sh
chmod 755 filename
```

### Changing Ownership:
Use `chown` to change owner and group.
```sh
chown user:group filename
```

---

## Package Management
### Debian-based (Ubuntu, Debian):
- Update packages:
  ```sh
  sudo apt update && sudo apt upgrade
  ```
- Install a package:
  ```sh
  sudo apt install package_name
  ```
- Remove a package:
  ```sh
  sudo apt remove package_name
  ```

### RedHat-based (RHEL, CentOS, Fedora):
- Update packages:
  ```sh
  sudo yum update
  ```
- Install a package:
  ```sh
  sudo yum install package_name
  ```
- Remove a package:
  ```sh
  sudo yum remove package_name
  ```

---

## Shell Scripting
A shell script is a file containing a series of commands.

### Example:
```sh
#!/bin/bash

echo "Hello, World!"
```
Save the file and make it executable:
```sh
chmod +x script.sh
./script.sh
```

---

## Linux LVM Volumes
Logical Volume Manager (LVM) helps in managing disk storage.

### Basic LVM Commands:
- Create a physical volume:
  ```sh
  pvcreate /dev/sdX
  ```
- Create a volume group:
  ```sh
  vgcreate my_vg /dev/sdX
  ```
- Create a logical volume:
  ```sh
  lvcreate -L 10G -n my_lv my_vg
  ```
- Format and mount:
  ```sh
  mkfs.ext4 /dev/my_vg/my_lv
  mount /dev/my_vg/my_lv /mnt
  ```

---

## Conclusion
This guide covers basic Linux administration topics including file permissions, package management, shell scripting, and LVM volumes.
