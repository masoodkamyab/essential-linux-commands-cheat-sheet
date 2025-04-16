## **File and Directory Management**

- **`cd`**  
  *Changes the current working directory to the specified path.*

- **`ls`**  
  *Lists the contents of a directory, including files and subdirectories.*

- **`touch`**  
  *Creates a new, empty file or updates the timestamp of an existing file.*

- **`pwd`**  
  *Prints the current working directory path.*

- **`cp`**  
  *Copies files or directories from one location to another.*

- **`mv`**  
  *Moves or renames files and directories.*

- **`rm`**  
  *Removes (deletes) files or directories (with the proper flags).*

- **`mkdir`**  
  *Creates a new directory with the specified name.*

- **`rmdir`**  
  *Removes an empty directory.*

- **`find`**  
  *Searches for files and directories matching specified criteria.*

- **`tree`**  
  *Displays directory contents in a tree-like format.*

- **`stat`**  
  *Displays detailed information about a file or file system object.*

---

## **File Viewing and Editing**

- **`cat`**  
  *Concatenates and displays file content to the standard output.*

- **`less`**  
  *Views file content one screen at a time with backward/forward navigation.*

- **`more`**  
  *Pages through text one screen at a time, typically for simple viewing.*

- **`head`**  
  *Displays the first few lines of a file (default is 10 lines).*

- **`tail`**  
  *Displays the last few lines of a file (default is 10 lines).*

- **`nano`**  
  *A simple and user-friendly text editor for the terminal.*

- **`vi`**  
  *A powerful text editor with modal editing (often used interchangeably with vim).*

- **`vim`**  
  *An enhanced version of vi offering more features and customization options.*

- **`cut`**  
  *Extracts sections from each line of a file (usually by column or delimiter).*  

- **`sort`**  
  *Sorts lines of text in a file or input stream.*

- **`uniq`**  
  *Filters out repeated lines from a sorted file or input stream.*

- **`wc`**  
  *Counts lines, words, and characters in a file or input stream.*

- **`diff`**  
  *Compares the contents of two files line by line and shows their differences.*

- **`tee`**  
  *Reads from standard input and writes to both standard output and one or more files simultaneously.*

---

## **File Permissions and Ownership**

- **`chmod`**  
  *Changes the file access permissions.*

- **`chown`**  
  *Changes the owner and/or group of a file or directory.*

- **`chgrp`**  
  *Changes the group ownership of a file or directory.*

- **`umask`**  
  *Sets the default permission or creation mask for newly created files and directories.*

- **`lsattr`**  
  *Lists the attributes of files on a Linux file system, such as immutable flags.*

- **`chattr`**  
  *Changes file attributes on a Linux file system (e.g., making a file immutable).*

---

## **Disk and System Usage**

- **`du`**  
  *Estimates and reports the disk space used by files and directories.*

- **`df`**  
  *Reports the amount of disk space available on mounted filesystems.*

- **`free`**  
  *Displays the amount of free and used memory in the system.*

- **`uptime`**  
  *Shows how long the system has been running, along with load averages.*

- **`lsblk`**  
  *Lists information about all available block devices in a tree-like format.*

- **`mount`**  
  *Mounts a file system (makes it accessible for use).*

- **`umount`**  
  *Unmounts a file system, disconnecting it from the directory structure.*

- **`fsck`**  
  *Checks and repairs Linux file systems for errors.*

---

## **System Monitoring**

- **`top`**  
  *Displays real-time system processes, resource usage, and performance statistics.*

- **`htop`**  
  *Provides an interactive, more user-friendly view of the processes and system usage.*

- **`ps`**  
  *Reports a snapshot of current active processes.*

- **`kill`**  
  *Sends signals to processes, commonly used to terminate them.*

- **`killall`**  
  *Kills processes by name rather than by process ID (PID).*

- **`jobs`**  
  *Lists the active jobs started in the current terminal session.*

- **`bg`**  
  *Resumes a paused job in the background.*

- **`fg`**  
  *Brings a background job to the foreground.*

---

## **Networking**

- **`ping`**  
  *Sends ICMP echo requests to test connectivity to another network host.*

- **`curl`**  
  *Transfers data to or from a server using various protocols (e.g., HTTP, FTP).*

- **`wget`**  
  *Downloads content from the web non-interactively via HTTP, HTTPS, or FTP.*

- **`ifconfig`**  
  *Displays or configures network interface parameters (being replaced by `ip`).*

- **`ip`**  
  *Shows and manipulates routing, devices, policy routing, and tunnels (replacement for ifconfig).*

- **`netstat`**  
  *Displays network connections, routing tables, interface statistics, and more.*

- **`ss`**  
  *Displays detailed socket statistics and is faster than netstat.*

- **`nc` (netcat)**  
  *Reads and writes data across network connections using TCP or UDP (often used for debugging).*

- **`scp`**  
  *Securely copies files between hosts over a network using SSH.*

- **`rsync`**  
  *Synchronizes files and directories between two locations efficiently.*

- **`tcpdump`**  
  *Captures and analyzes network packets transmitted over a network interface.*

- **`traceroute`**  
  *Traces the network path taken by packets to a specified host.*

---

## **Searching and Filtering**

- **`grep`**  
  *Searches text for specified patterns using regular expressions.*

- **`awk`**  
  *A powerful programming language for pattern scanning and processing of text files.*

- **`sed`**  
  *A stream editor used to perform basic text transformations on an input stream.*

- **`cut`**  
  *Extracts sections of input lines by field or character position (also useful in filtering).*  

- **`tr`**  
  *Translates or deletes characters from the input data.*

---

## **System Management**

- **`shutdown`**  
  *Shuts down or reboots the system safely according to the specified parameters.*

- **`reboot`**  
  *Restarts the system immediately.*

- **`systemctl`**  
  *Controls and manages systemd services and the system state.*

- **`service`**  
  *Manages services on System V init or compatible systems with a simpler interface.*

- **`journalctl`**  
  *Queries and displays logs from the systemd journal.*

- **`history`**  
  *Displays the history of commands entered in the current shell session.*

- **`alias`**  
  *Creates shortcuts for commands, allowing easier or alternative command names.*

- **`export`**  
  *Sets environment variables so that they are available to child processes.*

---

## **Package Management (Debian/Ubuntu-based systems)**

- **`apt update`**  
  *Updates the list of available packages and their versions (does not install or upgrade packages).*

- **`apt upgrade`**  
  *Upgrades all installed packages to their latest available versions.*

- **`apt install`**  
  *Installs new packages along with their dependencies from repositories.*

- **`apt remove`**  
  *Removes installed packages from the system, while preserving configuration files by default.*

- **`dpkg`**  
  *A low-level tool for managing Debian packages, allowing manual installation and removal.*

---

## **User and Permissions Management**

- **`sudo`**  
  *Runs a command with elevated privileges (administrator or root permissions).*

- **`su`**  
  *Switches to another user account, commonly used to assume the root identity.*

- **`whoami`**  
  *Prints the effective username of the current user.*

- **`id`**  
  *Displays the current user’s ID and associated group IDs.*

- **`passwd`**  
  *Changes the user account password for the current or specified user.*

- **`groupadd`**  
  *Creates a new user group on the system.*

- **`useradd`**  
  *Creates a new user account along with an optional home directory and initial settings.*

- **`groupdel`**  
  *Deletes an existing group from the system.*

- **`userdel`**  
  *Deletes a user account, with options to remove the home directory and mail spool.*

---

## **Utilities and Miscellaneous**

- **`echo`**  
  *Prints text or variables to the standard output.*

- **`date`**  
  *Displays or sets the system date and time.*

- **`man`**  
  *Opens the manual pages for commands to provide detailed documentation and usage information.*

- **`env`**  
  *Displays a list of environment variables or runs a command with a modified environment.*

- **`who`**  
  *Lists users currently logged into the system and their login details.*

- **`w`**  
  *Shows who is logged on and what each user is currently doing.*
