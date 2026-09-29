# Week 02: Linux Fundamentals

**Dates:** 14 Sep 2026 to 20 Sep 2026

## Summary
This week covered the Linux basics every cloud engineer needs: how the file system is laid out, how to navigate it from the 
terminal, how users, groups and permissions control access, how processes run, and how to install software with a package 
manager. I also practiced connecting to a machine over SSH and mounting a fake disk.

## What I Learned
### Operating systems and Linux
An operating system sits between hardware and software and manages memory, processing and devices. Every cloud server (EC2, 
Azure VM, Compute Engine) runs one, most often Linux. Linux is an open source OS created by Linus Torvalds in 1991. A distro 
(Ubuntu, Debian, Fedora, RHEL) is a full OS built on the Linux kernel. The kernel talks to the hardware, and the shell (such 
as bash) is how I give it commands from the terminal.

### File system and navigation
Linux has one tree starting at `/`, with no drive letters. Key folders: `/etc` for configuration, `/home` for user files, 
`/var` for logs and changing data, `/tmp` for temporary files, `/bin` and `/sbin` for programs, `/usr` for installed 
software, and `/dev` for devices.

Core commands: `pwd`, `ls`, `cd`, `mkdir`, `touch`, `rm`, `cp`, `mv`, `cat`, `less`, `head`, `tail`, `clear`. For help, use 
`man <command>` or `<command> --help`. To edit files, use `nano` (save with Ctrl+O, exit with Ctrl+X) or `vi` (press `i` to 
insert, Esc, then `:wq` to save and quit).

### Users, groups and permissions
A user is an account for a person or a service, stored in `/etc/passwd` with a UID, home directory and shell. System 
users like `www-data` exist so each service runs with limited permissions. A group is a collection of users so 
permissions can be managed in one place. Every user has one primary group and can have several secondary groups 
(listed in `/etc/group`).

Useful commands: `whoami`, `id`, `groups alice`, `sudo adduser john`, `groupadd cloud`, `usermod -aG developers 
alice`, `gpasswd -d alice developers`, `passwd alice`, `su - alice`. Always use `-a` with `-G`, because `usermod -G` 
without `-a` replaces all secondary groups and can remove someone from `sudo`.

Permissions are read (r), write (w) and execute (x) for the owner, the group and others. In numbers, r is 4, w is 2 
and x is 1, so `chmod 640 file` gives the owner read and write, the group read, and others nothing. Symbolic form also 
works, for example `chmod u+x` script.sh. To change ownership, use `chown user:group file`. Check with `ls -l`.

### Processes
A process is a running program. Processes form a parent and child tree. A daemon runs in the background, an orphan 
is a child whose parent ended (systemd adopts it), and a zombie has finished but its parent has not read its exit 
status yet. Useful commands: `ps aux`, `top`, `htop`, `kill <PID>`, `killall <name>`, `bg`, `fg`, and `sleep 100 &` 
to run something in the background.

### Packages, SSH and mounting
Package managers install and remove software: `apt` on Debian and Ubuntu, `yum` or `dnf` on Red Hat family systems. 
Common apt commands are `sudo apt update`, `sudo apt install nginx`, `sudo apt remove nginx` (keeps config files) 
and `sudo apt purge nginx` (removes configs too).

SSH gives a secure, encrypted remote shell into another machine with `ssh user@ip`. It is how I reach VMs, droplets and EC2 
instances.

Mounting attaches a disk or storage to a folder in the file tree. Linux uses `mount` and `umount` instead of drive letters.

## What I Did (Hands On)
Practiced user and permission commands:
```bash
# touch test.txt
# ls -l test.txt
# chmod 640 test.txt
# sudo chown alice:devs test.txt
# ls -l test.txt
```
Installed and checked NGINX:
```bash
# sudo apt update
# sudo apt install nginx -y
```
Created and mounted a fake 100MB disk:
```bash
# fallocate -l 100M disk.img
# mkfs.ext4 disk.img
# sudo mkdir /mnt/fakedisk
# sudo mount disk.img /mnt/fakedisk
# df -h /mnt/fakedisk
# sudo umount /mnt/fakedisk
```

## Resources Used
- Linux Management for Cloud Engineering, Part 1 (Medium)
- chmod command in Linux (Linuxize)
- How to create users with useradd (Linuxize)
- Linux commands cheat sheet (GeeksforGeeks)
- OverTheWire Bandit
- Altschool course videos Class on Linux Fundamentals

