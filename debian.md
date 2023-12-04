# Add user to sudoers

By default the users are not sudoers. To add a user to sudoers groups, you need to be root (⚠️ "su -" not "su" otherwise you won't be able to use the usermod command). Then install sudo and add the user to the sudo group.
```sh
su -
apt update && apt upgrade
apt install sudo
usermod -aG sudo <username>
```

⚠️ You may restart the shell to get the access to the sudo group.
# Install basic commands

```sh
sudo apt update && sudo apt upgrade
sudo apt install curl vim
```

# Add basic aliases

```sh
echo 'alias ..="cd .."' >> ~/.bashrc
```
