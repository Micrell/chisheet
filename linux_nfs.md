## Step 1: Update the System 

```bash 
sudo apt update sudo apt upgrade
```
## Step 2: Install Required Packages

```sh
sudo apt install nfs-kernel-server vim
```
## Step 3: Configure the NFS Service

- **Enable the service to start on boot:**
```sh
sudo systemctl enable nfs-kernel-server.service
```

- **Check the service status:**
```sh
sudo systemctl status nfs-kernel-server.service
```
_You should see that the service is active._

## Step 4: Configure the Shared Directory

- **Change ownership and permissions:**
```sh
sudo chown nobody:nogroup /srv/sharediso sudo chmod 755 /srv/sharediso
```

- **Verify permissions:**
```sh
ls -l /srv
```
## Step 5: Configure NFS Exports

- **Edit the `/etc/exports` file:**
```sh
sudo vim /etc/exports
```

- Add the following line:
`/srv/sharediso 192.168.1.0/24(ro,sync,anonuid=65534,anongid=65534,no_subtree_check)`

- **Check the file contents:**
```sh
cat /etc/exports
```
## Step 6: Apply the Configuration

- **Export the new configuration:**
```sh
exportfs -a
```

- **Purge existing exports if necessary:**
```sh
exportfs -ua
```
## Step 7: Verify Available Shares

- **List the shares available on the NFS host:**
```sh
showmount -e 192.168.1.113
```
## Step 8: Download an ISO File into the Shared Directory

- **Navigate to the shared directory:**
```sh
cd /srv/sharediso
```

- **Download the ISO file:**
```sh
sudo wget https://releases.ubuntu.com/noble/ubuntu-24.04.1-desktop-amd64.iso
```

