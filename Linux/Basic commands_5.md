# User Management Commands

## adduser — Create a User

- `adduser` is used to create a new user account.

```bash
sudo adduser john
```
- This creates a user named **john** and usually guides you through setting a password and other account information.

---

## useradd — Create a User

- `useradd` is also used to create a new user account, but it is generally a lower-level command with fewer interactive prompts.

```bash
sudo useradd john
```

- Create a user with a home directory:

```bash
sudo useradd -m john
```
- Set a password:

```bash
sudo passwd john
```

---

## adduser vs useradd 
- **adduser** → more user-friendly, interactive utility.
- **useradd** → lower-level command with more options and manual configuration.

---

## deluser — Delete a User 

deluser` is used to remove a user account.

```bash
sudo deluser john
```
This removes the user account but normally leaves the user's home directory.
To remove the user's home directory as well:
```bash
d sudo deluser --remove-home john
