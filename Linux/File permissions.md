# Linux File Permissions

## 1. What are File Permissions?

Linux controls who can access a file or directory and what they can do with it.

Run:

```bash
ls -l
```

### Example:

```
drwxr-xr-x  2 kali kali 4096 Sep 28 test
```

The permission section is:

```
drwxr-xr-x
```

### Break it down:

| Symbol | Description |
|---------|--------------|
| d       | Directory    |
| rwx     | Owner's permissions |
| r-x     | Group's permissions |
| r-x     | Others' permissions |

It can be broken down as:
- `d` : File type (Directory)
- `rwx` : Owner permissions (Read, Write, Execute)
- `r-x` : Group permissions (Read, No Write, Execute)
- `r-x` : Others permissions (Read, No Write, Execute)

### File Type Symbols:
| Symbol | Meaning |
|---------|---------|
| -       | Regular file |
| d       | Directory |
| l       | Symbolic link |

---

## 2. Permission Types

There are three basic permissions:

| Permission | Symbol | Meaning |
|------------|--------|---------|
| Read       | r      | Read/view |
| Write      | w      | Modify/Write |
| Execute    | x      | Execute a program/file |

For directories, `x` has a slightly different meaning: it allows you to enter/traverse the directory.

---

## 3. Who Gets the Permissions?

Linux divides permissions into:

- `u` → user/owner
- `g` → group
- `o` → others

### Example:
`-rwxr-xr--`

means:

- **Owner**  → `rwx`
- **Group**  → `r-x`
- **Others** → `r--`

Therefore:

- Owner can read, write, and execute.
- Group can read and execute.
- Others can only read.


---

## 4. Understanding +, - , =

These are used with `chmod`.

| Symbol | Meaning |
|---------|---------|
| +       | Add permission |
| -       | Remove permission |
| =       | Set permissions exactly |

---


## 5. chmod — Change Permissions

`chmod` = change file permissions

### Syntax
```
chmod [who][operator][permission] filename
```

### Add permission

Give the owner execute permission:

```bash
chmod u+x filename
```

**Breakdown:**
- `u` → owner
- `+` → add
- `x` → execute

### Remove permission

Remove write permission from the group:

```bash
chmod g-w filename
```
**Breakdown:**
- `g` → group
- `-` → remove
- `w` → write 
 
### Set permission 
 
Set owner's permission to read only:
 
```bash 
chmod u=r filename 
```
> [!note]
> `=` means set the specified permissions, rather than simply adding/removing one permission.

---

## 6. Numeric Permissions

Permissions also have numbers:

- `r` = 4
- `w` = 2
- `x` = 1

Add them together to determine permissions:

| Permission | Numeric Value |
|--------------|--------------|
| `r--`       | 4            |
| `-w-`       | 2            |
| `--x`       | 1            |

Combine permissions by adding their values:

- `rw-` = 4 + 2 = **6**
- `r-x` = 4 + 1 = **5**
- `rwx` = 4 + 2 + 1 = **7**

### Example

```bash
chmod 755 script.sh
```

This means:

- **7** → `rwx` → Owner permissions
- **5** → `r-x` → Group permissions
- **5** → `r-x` → Others permissions

Therefore, the permission code is: **755** which corresponds to **rwxr-xr-x**.

---

## 7. chown — Change Ownership

**chown** = change owner

### Change owner
```bash
sudo chown kali filename
```

Changes the owner to `kali`.

### Change owner + group
```bash
sudo chown kali:root filename
```

**Meaning:**
- Owner → `kali`
- Group → `root`

### Check using:
```bash
ls -l
```

> [!important]
> By default, the chown command changes the user and group ownership of only the single file or directory you specify on the command line

---

## 8. Practice

Don't stop after writing the notes. Immediately practice.

### Create a file
```bash
touch test.txt
```

### Check permissions
```bash
ls -l test.txt
```

### Add execute permission to owner
```bash
chmod u+x test.txt
```

### Check again
```bash
ls -l test.txt
```

### Remove execute permission
```bash
chmod u-x test.txt
```

### Change permission using numbers
```bash
chmod 644 test.txt
```
### Check:
```bash
ts -l test.txt
```

Then experiment with:
- `chmod 600 test.txt`
- `chmod 755 test.txt`
- `chmod 777 test.txt`

Don't just memorize what these numbers mean. Look at `ls -l` after each command and observe the change.
