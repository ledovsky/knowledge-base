# Управление пользователями в Linux

```bash
# Add and delete user
sudo adduser username
sudo deluser username

# Add group
sudo addgroup groupname

# Change password
passwd  # your user
sudo passwd username  # another user
sudo passwd  # root

# Add user to group
sudo usermod -a -G groupname username

# Add user to sudo
sudo usermod -a -G sudo username

# Change user directory
sudo usermod -d /srv/files/ftp ftp 

# Change owner of th directory (recursively)
sudo chown -R username:groupname /path/to/folder 

compgen -u  # list users
compgen -g  # list groups

getent group groupname  # list users of group

# Allowing group to access a directory
chgrp groupname ./foldername
chmod g+rwx ./foldername
```
