# Linux Command-Line Foundations - My learning Notes

## 1. Introduction

My objective was to understand how to navigate the filesystem, identify users, inspect running processes, examine network connections
and open ports on linux system and understand what was happening. The following are the commands that i have learnt and practiced

## 2. Navigating the filesystem

### Command and what I learned

1. 'pwd' - It displays my current working directory
2. 'ls' - Lists the files and directories
3. 'ls -la' - Displays detailed information and including hidden files
4. 'cd' - Changes my current directory
5. 'cd ..' - Moves one directory level backwards
6. 'cd ~' - Takes me back to my home directory
7. 'mkdir' - Creates a new directory

### Examples
'''bash
pwd
ls
ls -la
cd ..
cd ~
mkdir my folder
'''
### Lessons learnt
I can use these commands to understand where iam, inspect the directory contents and move around the linux filesystem

## 3. Understanding users

### Commands and what I have learned
1. 'whoami' - Displays the username of the currently logged-in-user
2. 'id' - Displays user and group identity inforamation

### Examples
'''bash
whoami
id
'''

### Lessons learnt 
Linux uses users and groups to manage access to files, directories and system resources

## 4. Understanding Running Processes

### Commands and what I learned

1. 'ps' - Displays information about running processes
2. 'ps aux' - Displays a detailed list of running processes
3. 'pgrep' - Finds processes by name
4. 'pstree' -  Displays processes in a parent-child tree
5. 'top' - Displays running processes and resources usage in real time

### Examples
'''bash
ps
ps aux
pgrep -af firefox
pstree -p
top
'''

### Lessons learnt 
A process is a running instance of a program. Linux operating system assigns each process a process ID (PID). I can use these commands to 
identify all running programs,inspect their activity and understand the relationship between parent and child processes
**Why does this matter for cybersecurity:** When investigating suspicious activity, one of the first things I need to establish is which processes are running 
who started them and how they relate to other processes

## 5. Understanding the Network interfaces and ip addresses
### Command and what I learnt
1. 'ip addr' - Displays networks interfaces and their ip addresses 
2. 'ip link' - Displays the network interface information 
3. 'ip route' - Displays the system routing table 
4. 'ip -6 addr' - Displays ipv6 addresses

### Examples
'''bash
ip addr
ip link show
ip route
ip -6 addr
'''
### Lessons Learnt 
Network interfaces connect my computer to networks. IP addresses identify devices or interfaces on a network, while routing information helps determine where network traffic
should go 

## 6. Understanding Network Connections and open ports
### Commands used and what i learnt 
1. 'ss -tuln' - Displays listening TCP ans UDP sockets without resolving service names
2. 'ss -tun' - Displays TCP and UDP socket information.
3. 'ss -tulnp' - Dispalys listening sockets and the associated process information
4. 'lsof' - Lists open files and can help identify processes using network sockets

### Examples
'''bash
ss -tuln
ss -tun
sudo ss -tulnp
sudo lsof -i
'''
### Understanding the options in ss -tulnp:
1. -t - Represent TCP sockets 
2. -u - Represents UDP sockets
3. -l - Listening sockets
4. -n - Show numerical addresses and port numbers 
5. -p - show associated processes where permissions allow

### Lessons learnt 
A listening port is waiting for incoming network communication by inspecting listening ports, I can identify services that may be accepting connections on my 
machine and investigate which processes owns them

## 7. Understanding services
### Commands and what I learnt 
1. 'Systemctl status' - Checks the status of a system service 
2. 'Systemctl list-units --type=service' - Lists loaded service units

### Examples 
'''bash 
systemctl status NetworkManager
systemctl list-units --type=service
'''
### Lessons learnt
Services are programs running in the background and can provide functions to the operating system. I can use systemctl to inspect their status
and understand which services are running 

## 8. Understanding System logs
### Commands and what I learned 
1. 'journalctl' - Displays system journal logs
2. 'journalctl -b' - Displays logs from the current boot
3. 'journalctl -p err' - Filters journal messages by error priority

### Examples
'''bash
journalctl
journalctl -b
journalctl -p err
'''

### Lessons learnt 
System logs provide information about events, errors and service activity, they help me to investigate what happened on my linux machine and when it happened

## 9. Understanding installed Packages
1. 'dpkg - l' - This Lists installed debian packages 
2.  'dpkg -S' -  Identifies which installed packages owns a particular file 
3.  'dpkg -V' - This checks installed packages files for verification differences  

### Examples 
'''bash
dpkg -l
dpkg -S /usr/bin/wsdd
sudo dpkg -V wsdd 
'''
### Lessons learnt 
Package-management commands help me to identify installed software, determine where files came and check whether package files have verification differences

## 10. Working with command output 
### Command or operator and what I have learnt 
1. 'grep' - Searches text for matching patterns 
2. 'awk' - Processes and extract information from text
3. '|' (pipe) - Passes the output of one command to another

### Examples
'''bash
ps aux | grep firefox
dpkg -l | grep wsdd
'''
### Lessons learnt
I can combine commands to filter information and make it easier to investigate large amounts of terminal output 

## My Overall Learning 
Through these exercises, I learned that the linux command line is more than just a place to type commands. It is a very powerful environment for understanding
and managing a computer system 

### I have developed foundations in:
- Filesystem navigation
- User and group identification 
- Process inspection 
- Network interface inspection
- Service management 
- System log analysis
- Package identification and verification
- Filtering command output

These foundations have prepared me for practical linux and cybersecurity investigations

## 12. My Next learning goals
I want to continue developing my linux skills by practising
- Linux file permissions and ownership
- Managing processes
- Understanding TCP and UDP connections
- Network troublesshooting
- Bash scripting
- Linux system hardening 
- Security monitoring and investigation 
