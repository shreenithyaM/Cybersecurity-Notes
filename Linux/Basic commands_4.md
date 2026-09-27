# Command Line Operations

## mv — Move / Rename
- `mv` is used to move or rename files and directories.

```bash
mv old.txt new.txt
```
- Renames `old.txt` to `new.txt`.

```bash
mv file.txt Documents/
```
- Moves `file.txt` into the `Documents` directory.

---

## cp — Copy
- `cp` is used to copy files and directories.

```bash
cp file.txt backup.txt
```

- Creates a copy of `file.txt` named `backup.txt`.

```bash
cp file.txt Documents/
```
- Copies `file.txt` into `Documents/`.
- To copy a directory and its contents:

```bash
cp -r Projects Projects_backup
```

---

## grep — Search Text 
- grep searches for specific text inside files.

```bash
grep "Linux" notes.txt
```
- displays lines in `notes.txt` containing "Linux".

- Case-insensitive search:
```bash
grep -i "linux" notes.txt
```
- Search multiple files:
```bash
grep "Linux" file1.txt file2.txt
```

---

## find — Find Files and Directories
- find searches the filesystem for files and directories.

### Examples of using `find`

- Find `notes.txt` starting from the current directory:

```bash
find . -name "notes.txt"
```

- Find all `.txt` files:

```bash
find . -name "*.txt"
```

- Find only files:

```bash
find . -type f -name "*.txt"
```

- Find only directories named "Projects":

```bash
find . -type d -name "Projects"
```

---

## locate — Quickly Find Files
- `locate` searches a database of file paths.

### Example:
```bash
locate notes.txt
```
- It can be faster than `find`, but the database may not contain newly created files until it is updated.

---

## zip — Compress Files
- zip is used to compress files and directories into a `.zip` archive.

### Create a ZIP file

```bash
zip files.zip file1.txt file2.txt
```
- This creates `files.zip` containing `file1.txt` and `file2.txt`.

### Zip a directory

```bash
zip -r Projects.zip Projects/
```

- `-r` means recursive, so all files and subdirectories inside `Projects` are included.

## View the contents of a ZIP file

```bash
unzip -l files.zip
```

## Extract a ZIP file

```bash
unzip files.zip
```

---

## wget — Download Files
- wget is used to download files from the internet using a URL.

### Download a file

```bash
wget https://example.com/file.txt
```
- The file is downloaded to the current directory.

### Save with a different name

```bash
wget -O newfile.txt https://example.com/file.txt
```
- `-O` specifies the output filename.

### Download in the background

```bash
wget -b https://example.com/file.zip
```
- `-b` runs the download in the background.
