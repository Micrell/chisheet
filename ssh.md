# scp

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

# ssh-add
## List keys linked to current ssh-agent
```sh
#List keys linked to current ssh-agent
ssh-add -l
```

# External link
https://www.ssh.com/academy/ssh/keygen