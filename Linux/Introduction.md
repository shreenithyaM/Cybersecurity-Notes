## Linux
Linux is a free and open-source operating system based on Unix.

- Created by Linus Torvalds (1991).
- Used in servers, supercomputers, Android, and embedded systems.

### Kernel
The kernel is the core of Linux; it manages CPU, memory, processes, and devices.

---

## Key Features
- Open source
- Multi-user
- Multitasking
- Secure and stable
- Portable

---

## Linux Distributions
A Linux distribution (distro) is Linux bundled with software and tools.
- **Ubuntu** — Beginner-friendly
- **Debian** — Stable
- **Fedora** — Modern features
- **RHEL** — Enterprise
- **Kali Linux** — Security and penetration testing

---

## Users & Permissions
### Users
to be added here if needed.
- `root` — Superuser with full privileges.
- Regular user — Limited privileges.
- System user — Used by services/processes.

### File Permissions
to be added here if needed.
- r = Read  
- w = Write  
- x = Execute
  
Permission Categories:
- u = Owner  
- g = Group  
- o = Others

Example:
- rwxr-xr--
  - Owner → rwx  
  - Group → r-x  
  - Others → r--

---

## Update Kali Linux
``` sudo
sudo apt update && sudo apt upgrade
```
apt update → Refresh package lists;
apt upgrade → Install available updates.

## Open Website using terminal
```sudo
firefox <URL>
```

e.g., firefox https://github.com

---

## Cybersecurity-Focused Linux Distributions

- Kali Linux — The most well-known security distro; focused on penetration testing, vulnerability assessment, forensics, and security tools.
- Parrot Security OS — Security-focused distro with penetration-testing, privacy, forensics, and development tools. Generally a bit more lightweight than Kali.
- BlackArch Linux — Arch-based distro with a very large collection of penetration-testing tools. Better suited to experienced Linux users.
- Tails — Privacy/anonymity-focused rather than penetration-testing-focused. Runs from removable media and minimizes traces on the computer.
