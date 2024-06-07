
# Installation (On VM)

https://minikube.sigs.k8s.io/docs/start/

## Step 1: Install Docker

See [[installation]]

## Step 2: Install Minikube

Pour Linux :
```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

Pour MacOS (apple silicon) :
```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-arm64
sudo install minikube-linux-arm64 /usr/local/bin/minikube
```

## Step 3: Add User to Docker group

```sh
sudo usermod -aG docker $USER && newgrp docker
```

## Step 4: Start Minikube

```sh
minikube start
```

## Step 5: Install Kubectl

```shell
minikube kubectl -- get po -A
alias kubectl="minikube kubectl --"
```

Do not forget to add the alias in `~/.bashrc` see [[alias]]
# Uninstallation

## Step 1: Stop the Minikube Cluster

Before uninstalling Minikube, ensure that the Minikube cluster is stopped.

```sh
minikube stop
```
## Step 2: Delete the Minikube Cluster

Once stopped, you can delete the Minikube cluster. This action will remove all the resources associated with the cluster.
```sh
minikube delete
```
## Step 3: Uninstall Minikube Binary

Now, you can remove the Minikube binary from your system.
```sh
sudo rm -rf /usr/local/bin/minikube
```
## Step 4: Remove Minikube Configuration and Files

Minikube stores its configuration and VM files in the .minikube directory in the user’s home directory. To remove these files:
```sh
rm -rf ~/.minikube
```
## Step 5: Uninstall Kubectl (Optional)

If you installed kubectl alongside Minikube and no longer need it, you can uninstall it as well.
```sh
sudo rm -rf /usr/local/bin/kubectl
```
