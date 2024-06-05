# Copy

Copy file:
```sh
scp filename user@server:/path/to/filename
```

Copy dir:
```sh
scp -r dirname user@server:/path/to/dirname
```

# Add an authorized key

## Generate key

On your PC, generate a new key, for exemple:
```sh
ssh-keygen -t ecdsa -b 521 -C "myPC"
```

Then copy your .pub key in `.ssh/authorized_keys` on the server:
⚠️ Ensure that `PubkeyAuthentication yes` is uncomment in `/etc/ssh/sshd_config`
You may restart the `sshd`service if modifications where needed in sshd config file.
You can also add `IdentityFile myprivatekey`to the server host in `~/.ssh/config`.
# ssh-add

## Add permanent private key

Add `IdentifyFile`option to Host in `~/.ssh/config`
```
Host github.com
    User git
    IdentityFile ~/.ssh/githubKey
```
## List keys linked to current ssh-agent
```sh
#List keys linked to current ssh-agent
ssh-add -l
```

# ssh-keygen
## Choose the encryption
```sh
#Choose the encryption
ssh-keygen -t rsa -b 4096
ssh-keygen -t dsa
ssh-keygen -t ecdsa -b 521
ssh-keygen -t ed25519
```

## Choose the file to store the key
```sh
#Choose the file to store the key
ssh-keygen -f ~/tatu-key-ecdsa -t ecdsa -b 521
```

## Add a comment attach to the key
```sh
#Add a comment attach to the key
ssh-keygen -t ecdsa -b 521 -C "comment"
```

# External link
https://www.ssh.com/academy/ssh/keygen