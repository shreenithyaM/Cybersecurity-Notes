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
