# Linux — Entering Data into Files

## 1. echo — Write Text from the Terminal
- Imagine you want to quickly write a message on the screen or save some text into a file.
- In Linux, `echo` is used to display text on the terminal or write text into a file.

### Display Text
```bash
echo "Hello Linux"
```

**Output:**

<img width="195" height="55" alt="image" src="https://github.com/user-attachments/assets/5eb1d392-574a-40e9-82f7-a38a0f429816" />

- Here, `echo` simply prints the text on the terminal.


### Write Text into a File
```bash
echo "Hello Linux" > file.txt
```

Now check the file:
```bash
cat file.txt
```

**Output:**

<img width="283" height="104" alt="image" src="https://github.com/user-attachments/assets/ad4dabf1-385c-4f2e-92d8-43a36cee6fab" />

**>** → Write the text into the file

### Add More Data
To add new text without removing the existing content, use `>>`.
```bash
echo "I am learning Kali Linux" >> file.txt
```

**Output:**

<img width="403" height="307" alt="image" src="https://github.com/user-attachments/assets/a6d3c323-6701-4f89-81e3-db05a3467878" />


**>>** → Add text to the existing file

---

## 2. nano — Edit a File
- Imagine you want to open a text file, type something, and save it, just like using Notepad on a computer.
- In Linux, nano is a simple text editor that works inside the terminal.

### Open or Create a File
```bash
nano notes.txt
```

Now you are inside the Nano editor.

Type:
- `Linux is an operating system.`
- `I am learning Linux commands.`
- `I will use Linux for cybersecurity.`

### Save the File
- **Ctrl + O → Save the file**
- Press:`Enter`
- **Ctrl + X → Exit Nano**

## Check the File
After exiting Nano, use `cat` to see what you wrote:
```bash
cat notes.txt
```
Output:

<img width="312" height="134" alt="image" src="https://github.com/user-attachments/assets/0eb0eaaa-8fdd-4597-97cb-128853c3d6e4" />

<img width="1343" height="524" alt="image" src="https://github.com/user-attachments/assets/1af10a1b-4f55-4707-9023-2d8da6064178" />


---

## 3. Touch vs Echo vs Nano

This distinction is important.

- touch - Creates an empty file.
- echo - Good for quickly putting small amounts of text into a file.
- nano - Good when you want to manually write/edit multiple lines.

---

## 4. Using `cat > file`

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

<img width="347" height="294" alt="image" src="https://github.com/user-attachments/assets/1b16add5-fe10-4808-9aea-8bccc497b8e8" />


> [!note]
> - `touch` → create empty file 
> - `echo` → quickly write/append text 
> - `nano` → manually edit a file 
> - `cat > file` → enter multiple lines through terminal 
> - `cat file` → read/display file
