# Linux — Entering Data into Files

## 1. echo — Write text from the terminal

### Display text
```bash
echo "Hello Linux"
```

**Output:**

```
Hello Linux
```

Here, `echo` simply prints text to the terminal.

### Write into a file
```bash
echo "Hello Linux" > file.txt
```

Check:
```bash
cat file.txt
```
**Output:**
```
Hello Linux
```

### Add more data
```bash
echo "I am learning Kali Linux" >> file.txt
```
Check:
```bash
cat file.txt
```
**Output:**
```
Hello Linux
I am learning Kali Linux
```
**Important:** `>` vs `>>`
- `>` replaces the existing content.
- `>>` adds to the existing content.

For example:
```bash
echo "First" > test.txt
echo "Second" > test.txt  # Overwrites previous content, so only "Second" remains.
```
to see the result:
```bash
cat test.txt  # Output: Second 
```
due to overwrite.
Now:
```bash
echo "First" > test.txt
echo "Second" >> test.txt  # Appends second line.
```
gives:
```plaintext
First
Second
```
---

## 2. nano — Edit a file

Nano is a simple terminal text editor.

## Create/open a file:

```bash
nano notes.txt
```

Now you are inside the editor.

Type:

```
Linux is an operating system.
I am learning Linux commands.
I will use Linux for cybersecurity.
```

## Save the file:

Press:

- `Ctrl + O`

Nano will ask for the filename.

Press:

- `Enter`

## Exit Nano:

Press:
- `Ctrl + X`

Now check the content of the file:

```bash
type cat notes.txt
defaults to see the content you entered.```
```
---

## 3. Touch vs Echo vs Nano

This distinction is important.

## touch

Creates an empty file.

## echo

Good for quickly putting small amounts of text into a file.

## nano

Good when you want to manually write/edit multiple lines.

---

### Using `cat > file`

You can also enter multiple lines directly from the terminal:

```bash
cat > test.txt
```

Now type:

```
Line 1
Line 2
Line 3
```

When finished, press:

```plaintext
Ctrl + D
```
Then:

```bash
test.txt> cat test.txt
```
You'll see the lines you entered.

> [!note]
> - `touch` → create empty file 
> - `echo` → quickly write/append text 
> - `nano` → manually edit a file 
> - `cat > file` → enter multiple lines through terminal 
> - `cat file` → read/display file
