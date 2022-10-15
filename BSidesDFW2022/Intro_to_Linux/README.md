# Introduction to Kali Linux - 2 hours

A fast paced introduction to the Linux operating system.  Learn to understand how Linux environments are most commonly set up.  Learn how to use the command line to explore the system, manipulate files, install/upgrade applications, and more.  This course is based on Kali Linux, but most aspects will extend to most Linux distributions.  
* This Course is a precursor to the other 2 classes taught by Lee Heath, ‘Introduction to Nmap’ and ‘Wifi Hacking with Wireshark’.
* This corse will not cover shell scripting or any of the common scripting languages.
* Live USBs will be provided.
* Laptop needed for hands on.

## Installation
- Follow the prompts
- Live Boot vs Install
- Partitioning - Why change the default

## Shells
- bash
    - CLI interface
    - tab completion
    - Prompts
        - Default:  <user>@<system> <location> $|#
- man/info
- --help
    - Most commands have a --help or a -h option to explain basic options
- --version
- which
    - Show where the command is.  Can be used to make sure you are calling the right version
- who/w/id
    - identify who you are and who is/has used the system
- env
    - Environment variables
    - Covered in detail in next Section
- Wildcards
    - \* for anything any number of times
    - ? for anyting 1 time
- passwd - CHANGE YOUR PASSWORD
- clear

## Environment
- Environment Variables
  - PATH - Used to specify the path to search for binaries when typing commands
  - _ - current command
  - VISUAL - Default editor for many apps that auto open and editor
  - USER - Current username
  - HOME - Your Home directory
  - SHELL - Current shell
  - PWD - Present Working Directory
- ~/.bashrc
  - Location to set environment variables and aliases
  - Shell script
  - Aliases
  - PATH
  - prompt
  - History
- Aliases
  - Simple replacements
  - commonly set up
    - ll = ls -l
    - la = ls -a

## Users vs Root
- User level access
    - PATH - will include binary locations such as /bin /usr/bin
    - Permission - Can only access files that have specific permissions for this user or any groups the user is part of.
- Root level access
    - PATH - will add locations like /sbin /usr/sbin
    - Permission - Can access almost any file on the system
- su - SuperUser
    - Needs the password (unless you are root)
    - Default superuser
    - Can be used to log into any user
      - su <username>
- sudo - SuperUser DO
    - Needs YOUR password
    - similar to runas
    - sudo -u <username> - run a command as another user

## Files
- Every thing is a file
    - You interact with everything as a file
    - Files can be devices
    - APIs or named Pipes
    - System Info from the Kernel or processes
    - Terminals
- Identifying a file
    - ls - LiSt files
        - Alias
        - Common options
        - -l - Long list
        - -a - List all files, including ones that are "hidden" that start with .
        - -d - list directories not the contents (see `ls *`)
        - -h - "human" readable
        - -t - sort by time
        - -S - sort by size
        - -r - reverse sorting
    - file - identify a FILE

## File Permissions
- What are file permissions?
```
$ ls -l /etc/services
-rw-r--r-- 1 root root 12813 Mar 27  2021 /etc/services
$ ls -l /bin/bash
-rwxr-xr-x 1 root root 1234376 Aug  4  2021 /bin/bash
```

  - Positions in the ls
    - ♦--------- - First is the file type
      - d is a directory
      - b is a block special file
      - c is a character special file
      - l is a symbolic link
      - p is a first-in,first-out (FIFO)
      - s is a local socket
      - \- is an ordinary file
    - -♦♦♦------ - These positions designate the permissions for the owner, the specific user
    - ----♦♦♦--- - These positions designate the permissions for the group, is a users is a part of the group
    - -------♦♦♦ - These positions designate the permissions for anyone
     - First position in all 3 is the READ permissions
      - r means read is enabled
      - \- means it is disabled
     - Second position is the WRITE permissions
      - w means write permissions are enabled
     - Third position is the EXCUTE permissions
      - x means execute permissions are enabled
  - /etc/services is readable by anyone and writable by root
  - /bin/bash is readable and executable by anyone and writable by root
- chown
- chmod
- chgrp

## Directory Structure
- Common places
    - /etc - config
    - /home - User home directories
    - /root - root home directory
    - /bin - Binaries
    - /dev - devices
    - /proc - processes
    - /tmp
    - /var
    - /usr
    - /usr/share
    - /usr/bin
    - /usr/sbin
    - /opt - optional
    - /mnt
- Movement within the Directory Structure
    - cd - Change Directory
    - pwd - Present Working Directory
    - ~ - Shortcut for $HOME
    - GUI - See DEMO
- Manipulation
    - mkdir - MaKe DIRectory
      - -p - creat all directories in the path that do not already exist
    - rmdir - ReMove DIRectory
      - Only is the directory is empty
      - -p - same as above, will remove all directories in the path if they are empty
- Manipulation
    - cat - concatenate - Send contents of a file to STDOUT in the order they are read
    - less/more - View (readonly) contents of a file with options for pagination, search, and other options
    - head - Display the top lines of a file
      - default is 10 lines
      - Specify number of lines to display
    - tail - Same as head, but for the bottom
    -

## Package Management
  - GUI
  - CLI
    - apt - Advanced Package Tool
      - wrapper for tools like apt-get apt-search
      - apt update - Update the package list from designated repos
      - apt upgrade - Upgrade packages that have an new package available
      - apt search - Search for a package
      - apt install - Install a specific package
      - apt remove - Uninstall a package
      - apt autoremove - Uninstall packages that are no longer necessary i.e. Old Kernels

## Command Line Output
- Types
  - STDOUT
  - STDERR
- Piping
  - \| used to send the output of one command to the input of another
  - Some commands will have to specify STDIN as the input, usually with -
- Redirection
  - \> - Used to redirect STDOUT
  - 2> - Used to redirect STDERR
  - 2>&1 - Used to redirect STDERR to STDOUT
  - tee - command to output to a file and STDOUT at the same time
- Chaining Commands



## Job management
- ^z  
- bg
- fg
- jobs

# Bonus: How to exit vim
- How to exit VI/VIM
    - Hit <esc> to make sure you are not in input mode
    - Type ':q' and it should appear in the bottom left  
    - This will tell vi to quit.
    - If it causes an error, it may say you have not saved.  If you wish to save back to the file before quiting type :wq
    - Thise will Write the file before Quiting.
    - If you want to just quit and not save changes type :q!
    - This will force (!) vi to Quit
