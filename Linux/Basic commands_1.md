# Linux Basic Commands — Kali Practice
> [!important]
> Don't just copy the command. First predict what will happen, then run it and observe.

---

## 1. pwd — Where Am I?
- Imagine you open Google Maps and tap “Your Location” to see where you are.
- In Linux, `pwd` does something similar — it tells you which directory (folder) you are currently in.

### Example
```bash
pwd
```

**Output:**

<img width="165" height="54" alt="image" src="https://github.com/user-attachments/assets/08959271-78a8-482f-99dd-fcbdf380230b" />

- This means you are currently inside the `/home/kali` directory.

---

## 2. ls — What’s Here?
- Imagine you open a folder on your computer and look at all the files and folders inside it.
- In Linux, `ls` does the same thing — it shows you what is inside the current directory.

### Example
```bash
ls
```

**Output:**

<img width="678" height="61" alt="image" src="https://github.com/user-attachments/assets/0c3599c6-c20a-405c-97db-866998c5c3ab" />

- This means these files and folders are inside your current directory.

- ls -a — Show Everything - Show all, including hidden files
- ls -l — Show More Details - Show details in a long format
- ls -la — Show Everything + Details - Show all files + detailed information

<img width="1191" height="509" alt="image" src="https://github.com/user-attachments/assets/566ee4a3-1546-4f7e-9d00-df08713a09ea" />
 
---

## 3. cd — (Change Directory) Go Somewhere Else

- Imagine you are using Google Maps and you choose a different location to go to.
- In Linux, `cd` helps you move from one directory (folder) to another.
```bash
cd /tmp
```
- This moves you to the `/tmp` directory.
- You can check your new location using:

```bash
pwd
```

**Output:**

<img width="197" height="91" alt="image" src="https://github.com/user-attachments/assets/6cb4b63b-db8b-4454-b317-d7a310c6f19d" />

### Go Into a Folder
Suppose you have a folder called *Documents*:

```bash
cd Documents
```

Now you are inside the *Documents* folder.

### Go Back
To go back to the previous directory:

```bash
cd ..
```

### Go to Home Directory
defaults to your home directory:
```bash
cd ~
```

<img width="244" height="232" alt="image" src="https://github.com/user-attachments/assets/096666a0-926e-45c6-a1b9-e2d2cbf4b64c" />

---
---

# Create directories/folders & files

## 4. mkdir — Create a New Folder

- Imagine you are on your computer and want to create a new folder to keep your files organized.
- In Linux, `mkdir` is used to create a new directory (folder).

### mkdir — Make a Directory
```bash
mkdir Projects
```
- This creates a new folder called **Projects**.

You can check it using:
```bash
ls
```

You should see:

<img width="318" height="265" alt="image" src="https://github.com/user-attachments/assets/f5f3b954-d88b-4ed2-9f5f-ee41995bca9f" />

### Create Multiple Folder 
```bash
mkdir Projects1 Projects2
```

<img width="246" height="175" alt="image" src="https://github.com/user-attachments/assets/4b9d923b-b4b3-4788-8ced-931e10e12b8f" />

> [!Note]
> Linux treats uppercase and lowercase letters as completely separate characters.
>
> This means that File.txt and file.txt are two entirely different files, and terminal commands must be typed with exact capitalization to work.

---

## 5. touch — Create a New File

- Imagine you create a new blank document on your computer before typing anything in it.
- In Linux, `touch` is commonly used to create a new empty file.

### touch — Create a File

```bash
touch notes.txt
```
- This creates a new empty file called `notes.txt`.

Check it using:

```bash
ls
```
You should see:

<img width="321" height="109" alt="image" src="https://github.com/user-attachments/assets/7dba7b87-b995-4192-a52b-f861ac44d9ba" />


### Create Multiple Files
You can create multiple files at once:

```bash
touch file1.txt file2.txt file3.txt
```
Check them:

```bash
ls
```

<img width="351" height="108" alt="image" src="https://github.com/user-attachments/assets/63bb0209-c89d-4992-8126-7de8452acb6a" />


---

## 6. cat — Read a File
- Imagine you have a text file on your computer and you open it to read what is written inside.
- In Linux, `cat` lets you see the contents of a file directly in the terminal.

### cat — Read a File

1. First, create a file:
2. Add some text to it:

```bash
echo "Hello Linux!" > notes.txt
```

Now use `cat`:

```bash
cat notes.txt
```

**Output:**

<img width="344" height="167" alt="image" src="https://github.com/user-attachments/assets/18c5af3b-2601-4c37-a611-41358c48d39e" />


> [!Important]
> - `cat` reads/displays the file.
> - `cat` does not modify the file when used normally.
