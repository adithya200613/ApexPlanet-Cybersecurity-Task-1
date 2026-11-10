# Linux Fundamentals

Linux is an open-source operating-system kernel used in distributions such as Kali Linux and Ubuntu. A shell provides a command-line interface.

## Important directories
- `/` – filesystem root.
- `/home` – users' home directories.
- `/etc` – configuration files.
- `/var` – variable data and logs.
- `/tmp` – temporary files.
- `/usr` – applications and shared resources.

## Permissions
Linux permissions use read (`r`), write (`w`) and execute (`x`) for owner, group and others. `sudo` runs an approved command with elevated privileges.

## Package management
```bash
sudo apt update
sudo apt upgrade
sudo apt install <package-name>
```

Understand commands before using `sudo`; avoid running unknown scripts as root.
