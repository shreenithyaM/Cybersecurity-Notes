Understanding Linux directories is important for Linux administration, troubleshooting, SOC/Blue Team work, and penetration testing. Many security investigations involve examining configuration files, users, processes, logs, devices, and temporary files.

# 1. `/` — Root Directory
The `/` directory is the top-level directory of the Linux filesystem.

- Every other directory is located somewhere underneath `/`.

**Example structure:**
``` text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── proc
├── root
├── tmp
├── usr
└── var
```
**Why it matters in cybersecurity:**
During security investigations or penetration testing, `/` provides the starting point for exploring the filesystem and understanding where sensitive files and system resources are located.

---

# 2. `/bin` — Essential User Commands
The `/bin` directory traditionally contains essential executable commands required for basic system operation.

**Examples include:**
- `ls`
- `cp`
- `mv`
- `cat`
- `pwd`
- `mkdir`
- `rm`

**Example usage:**

```bash
ls /
```

### Cybersecurity relevance
Attackers and defenders both encounter commands from this directory during command-line activity. Security monitoring can therefore involve tracking unusual execution of standard utilities.

---

# 3. `/sbin` — System Administration Commands

`sbin` traditionally contains commands primarily used for system administration.

## Examples:
- `fdisk`
- `reboot`
- `shutdown`
- `mkfs`

### Example:
```bash
ip addr
```

---

# 4. `/root` — Root User's Home Directory

`/root` is the home directory of the root user.
It is different from `/`, which is the root of the entire filesystem.

| Path | Description |
| --- | --- |
| `/` | Filesystem root |
| `/root` | Home directory of root user |

The root account is the traditional Linux superuser and has extensive privileges over the system.
You may encounter:
`sudo su`
To leave the root shell:
echo `exit`

### Cybersecurity relevance
The root account has powerful privileges, so unauthorized access to a root shell can have severe security consequences.
During penetration testing, privilege escalation refers to obtaining privileges beyond those originally available to the attacker.

---

# 5. `/etc` — System Configuration

`/etc` is one of the most important directories for Linux administration and cybersecurity.

It contains system-wide configuration files.

## Important examples:
- `/etc/passwd` - Contains information about local user accounts.
- `/etc/shadow` - Contains password-related authentication information, including password hashes on systems using traditional local password authentication.
Access is normally restricted.
- `/etc/hosts` - Provides local hostname-to-IP mappings.
- `/etc/hostname`
- `/etc/fstab`
- `/etc/group`
- `/etc/sudoers`

### Cybersecurity relevance
`/etc` is particularly important for:
- User enumeration
- Authentication investigation
- Misconfiguration detection
- Sudo privilege analysis
- Host/network configuration analysis
- Persistence investigation
- Incident response
> For example, defenders may examine configuration files for unexpected users, suspicious modifications, or overly broad privileges.

---

# 6. `/home` — Normal Users' Home Directories
`/home` generally contains the home directories of normal users.
Example:
- `/home/alex`
- `/home/john`
- `/home/user1`

---

# 7. `/var` — Variable Data
`/var` contains data that changes while the system is running.

**Examples include:**
- Logs
- Caches
- Spools
- Mail
- Application data
- Databases on some systems

### Cybersecurity relevance
`/var/log` is extremely important for SOC and Blue Team work.

Security analysts can investigate:
- Failed login attempts
- Successful authentication
- `sudo` usage
- SSH activity
- Service failures
- System events
-  Possible privilege escalation
-  Suspicious processes or activity

---

# 8. `/tmp` — Temporary Files 
`/tmp` is used for temporary files created by applications and users.

temporary files may be automatically removed according to the system's configuration, often during reboot or through periodic cleanup.

---

# 9. `/dev` — Device Files

Linux represents many devices and kernel interfaces through files under `/dev`.

## Examples:

- `/dev/sda`
- `/dev/sda1`
- `/dev/null`
- `/dev/tty`

## Some examples:

| Device File | Description |
|--------------|--------------|
| `/dev/sda` | disk device |
| `/dev/sda1` | partition |
| `/dev/null` | discards data |
| `/dev/tty` | terminal device |

## Important concept
Linux follows the principle:

> "Everything is a file"

This doesn't literally mean every object is an ordinary disk file, but many system resources can be accessed through file-like interfaces.

## Cybersecurity relevance
/Dev is important when investigating:
- Disk access
- Mounted storage
- Device activity
- Privileged operations
- Container environments

Some device files can provide powerful access to underlying resources, so their permissions matter.

---

# 10. `/proc` — Process and Kernel Information 

`/proc` is a virtual filesystem provided by the Linux kernel.

It doesn't primarily contain ordinary files stored on disk. Instead, it exposes information about:
- Running processes
- CPU
- Memory
- Kernel
- Hardware
- System configuration

## Example:

- `/proc/cpuinfo`
- `/proc/meminfo`
- `/proc/version`
- `/proc/uptime`

### Cybersecurity relevance
/proc is extremely useful for system enumeration and incident response.
You can investigate:
- Running processes
- Process IDs
- Process command lines
- Memory information
- Network-related information
- Process relationships

---

# 11. `/usr` — User Programs and Resources 
`/usr` contains a large portion of the system's user-space programs, libraries, and supporting resources.

## Common subdirectories include:
| Directory | Description |
| --- | --- |
| `/usr/bin` | Contains many user commands and executable programs |
| `/usr/sbin` | Contains many system-administration programs |
| `/usr/lib` | Contains libraries and other supporting files |
| `/usr/share` | Contains architecture-independent data such as documentation, icons, and other shared resources |
| `/usr/local` | Traditionally used for software installed locally by the system administrator rather than managed as part of the operating system's standard package set |

## Cybersecurity relevance 
defense analysts may examine /usr when:
detecting installed programs,
detecting suspicious binaries,
detecting modified system files,
and understanding available utilities.
