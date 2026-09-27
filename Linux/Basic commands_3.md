# rm and rmdir — Remove Files and Folders

- Imagine you have a file or folder you no longer need and want to delete it.
- In Linux, `rm` and `rmdir` are used to remove files and folders.

## 1. `rm` — (Remove) Remove a File

```bash
rm notes.txt
```
- This deletes the `notes.txt` file.
- **rm** → Delete a file

---

## 2. `rmdir` — (Remove Directory) Remove an Empty Folder

```bash
rmdir Projects
```
- This removes the `Projects` folder only if it is empty.
-  **rmdir** → Delete an empty folder

---

## 3. rm -r — Remove a Folder and Its Contents

- If the folder contains files or other folders, `rmdir` won't work.

## Use:
```bash
rm -r Projects
```
- Here, `-r` means recursive.
- It removes the folder and everything inside it.
- **rm -r** → Delete a folder and everything inside

---

## 4. rm -rf — Force Remove

`rm -rf` combines two options:
- `-r` → Recursive — remove the folder and everything inside.
- `-f` → Force — remove without asking for confirmation.

### Example:

```bash
rm -rf Projects
```
- This removes the **Projects** folder and all its contents forcefully.

> [!CAUTION]
>  **Be careful with `rm -rf`. Deleted files normally do not go to the Trash/Recycle Bin.**

---

## 5. * with rm — Select Multiple Files

- Imagine you have many files and want to select them based on their names.
- In Linux, `*` is a wildcard. It means “anything”.

### Remove Files Ending with `.txt`

```bash
rm *.txt
```

- This removes all files that end with `.txt`.

### Remove Files Starting with a Letter

Suppose you have:
- `notes.txt`
- `new.txt`
- `work.txt`
- `photo.jpg`

To remove files starting with `n`:

```bash
rm n*
```

This removes:
- `notes.txt`
- `new.txt`

but keeps:
- `work.txt`
- `photo.jpg`

> `n*` → Anything starting with n

### Remove Files Starting with "file"

to remove files starting with "file":

```bash
rm file*
```

For example:
- `file1.txt`
- `file2.txt`
- `file3.jpg`
- `notes.txt`

`rm file*` removes:
- `file1.txt`
- `file2.txt`
- `file3.jpg`
