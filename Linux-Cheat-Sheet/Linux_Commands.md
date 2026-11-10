# Linux Commands Cheat Sheet

## Navigation
| Command | Purpose |
|---|---|
| `pwd` | Show current directory |
| `ls -la` | List files including hidden files |
| `cd folder` | Change directory |
| `cd ..` | Move to parent directory |

## Files
| Command | Purpose |
|---|---|
| `mkdir folder` | Create directory |
| `touch file.txt` | Create empty file |
| `cat file.txt` | Display file |
| `nano file.txt` | Edit file |
| `cp source destination` | Copy |
| `mv source destination` | Move or rename |
| `rm file.txt` | Delete file |

## System and network
| Command | Purpose |
|---|---|
| `whoami` | Current username |
| `uname -a` | System information |
| `df -h` | Disk usage |
| `free -h` | Memory usage |
| `ip addr` | Network addresses |
| `ip route` | Routing table |
| `ping -c 4 IP` | Send four ping requests |
| `ss -tuln` | Show listening sockets |

## Processes
`ps aux` lists processes; `top` monitors them; `kill PID` sends a signal to a process.

## Lab commands
```bash
ping -c 4 192.168.56.101
nmap -sV 192.168.56.101
wireshark
openssl version
```
Use commands only on authorized systems. Be cautious with destructive commands and elevated privileges.
