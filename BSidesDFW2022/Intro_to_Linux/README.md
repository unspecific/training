# Introduction to Kali Linux

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
    - Environment variables,
- $PATH
    - Never add '.' in your path
- ~/.bashrc
    - Shell script
    - Alias
    - PATH
    - prompt
    - History
- Wildcards
    - * for anything any number of times
    - ? for anyting 1 time
- passwd - CHANGE YOUR PASSWORD
- clear

## Users vs Root
- User level access
    - PATH
- Root level access
    - PATH
- su - SuperUser
    - Needs the password (unless you are root)
    - Default superuser
    - Can be used to log into any user
- sudo - SuperUser DO
    - Needs YOUR password
    - similar to runas

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
    - pwd - Present WOrking DIrectory
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
- Piping
- Redirection
- Chaining Commands

## Environment
- Environment Variables
- Aliases
- ~/.bashrc

## File Permissions
- chown
- chmod

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
