# Linux Basic Commands — Kali Practice

> [!important]
> Don't just copy the command. First predict what will happen, then run it and observe.

---

## 1. **pwd** — Where am I?
Shows your current working directory.

### Practice:
```bash
pwd
```

Change directory to `/tmp` and check again:
```bash
cd /tmp
pwd
```

---

## 2. ls — What is here?

Lists files and directories.

```bash
ls
```

**Try:**
- `ls -l`
- `ls -a`
- `ls -la`

**Practice:**
- `ls`
- `ls -la`

**Understand:**
- `-l` → detailed information
- `-a` → includes hidden files
- Change directory to home (`~`) and check again:
```bash
cd ~
pwd
```

### Observe:
* How does the output change?

---

## 3. cd — Move around

```bash
cd /tmp
pwd
```

## Go back:

```bash
cd ..
pwd
```

## Go to home:

```bash
cd ~
pwd
```

## Practice:

```bash
cd /tmp
mkdir linux-practic
cd linux-practice
pwd
cd ..
pwd
```

---

# Create directories/folders & files

## 4. mkdir — Create directories

```bash
mkdir test
```

## Check:

```bash
ls
```

Create multiple directories:

```bash
mkdir one two three
```

---

## 5. touch — Create files

```bash
touch file.txt
```

## Check:

```bash
ls
```

## Create multiple:

```bash
touch one.txt two.txt three.txt
```

---

## 6. cat — Read a file
- **`cat`** stands for *concatenate*.
- It is mainly used to read and display the contents of a file.

## Syntax:

```bash
cat filename
```

## Example:

```bash
cat notes.txt
```

If `notes.txt` contains:

```
Linux is easy.
I am learning Linux.
```

The command displays:

```
Linux is easy.
I am learning Linux.
```

## Important Notes:
- `cat` reads/displays the file.
- `cat` does not modify the file when used normally.
