---
tags:
  - linux
---

# Show
```sh 
cat /etc/passwd # Show user database
cat /etc/group  # Show group database
```

# Add
```sh
useradd [options] <username>  # Create user
```

| options | comment                                    | example                                          |
| ------- | ------------------------------------------ | ------------------------------------------------ |
| -d      | Specify home dir                           |                                                  |
| -u      | Specify user UUID                          |                                                  |
| -g      | Specify initial login group UUID or name   |                                                  |
| -G      | Add user to multiple groups                | useradd -G sudo,docker,dev micrell               |
| -M      | Create user without creating it's home dir |                                                  |
| -c      | Add a custom comment                       | useradd -c "minecraft service account" minecraft |
| -r      | Create system user                         | useradd -rM minecraft                            |


# Remove
```sh
deluser <username>
```

| options | comment |
| --- | --- |

# Set user password
```
passwd <username>
```

| options | comment |
| --- | --- |

# Modify user properties
```sh
usermod [options] <username>
```

| options    | comment                      | example                         |
| ---------- | ---------------------------- | ------------------------------- |
| -s <shell> | Modify default shell of user |                                 |
| -a         | Append, to use with -G       |                                 |
| -G         | Add user to multiple groups  | usermod -aG sudo,docker micrell |


