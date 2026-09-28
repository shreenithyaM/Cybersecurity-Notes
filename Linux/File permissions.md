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

It can be broken down as:
- `d` : File type (Directory)
- `-` : File
- `rwx` : Owner permissions (Read, Write, Execute)
- `r-x` : Group permissions (Read, No Write, Execute)
- `r-x` : Others permissions (Read, No Write, Execute)

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

<img width="563" height="265" alt="image" src="https://github.com/user-attachments/assets/b9ccd483-0539-43cd-b892-68186ae83462" />

---

## 4. Understanding +, - , =

These are used with `chmod`.

| Symbol | Meaning |
|---------|---------|
| +       | Add permission |
| -       | Remove permission |
| =       | Set permissions exactly (add new, remove existing) |

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

<img width="424" height="303" alt="image" src="https://github.com/user-attachments/assets/83386f62-b97a-43c0-ab7a-a028bb7f3fd5" />


### Remove permission

Remove write permission from the group:

```bash
chmod g-w filename
```
**Breakdown:**
- `g` → group
- `-` → remove
- `w` → write 

<img width="429" height="169" alt="image" src="https://github.com/user-attachments/assets/290041ab-db80-49ad-ac90-63cbe66c200a" />

 
### Set permission 
 
Set owner's permission to read only:
 
```bash 
chmod u=r filename 
```

<img width="433" height="174" alt="image" src="https://github.com/user-attachments/assets/2b0e575d-d5e9-4703-b565-3da5b59319e5" />


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

<img width="418" height="303" alt="image" src="https://github.com/user-attachments/assets/f4f531db-ef96-4984-bfe8-af560d32819c" />


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
<img width="427" height="307" alt="image" src="https://github.com/user-attachments/assets/d19e8377-ee52-4411-b85a-f13073fd1929" />


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
