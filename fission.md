# Installation on [[minikube]]

## Step1: Install Helm

see [[helm]]

## Step2:  Install Fission with Helm

```sh
export FISSION_NAMESPACE="fission"
kubectl create namespace $FISSION_NAMESPACE
kubectl create -k "github.com/fission/fission/crds/v1?ref=v1.19.0"
helm repo add fission-charts https://fission.github.io/fission-charts/
helm repo update
helm install --version v1.19.0 --namespace $FISSION_NAMESPACE fission \
  --set serviceType=NodePort,routerServiceType=NodePort \
  fission-charts/fission-all
```

## Step3: Install Fission CLI

```ad-warning
THE OFFICAL DOC FOR LINUX IS Linux AMD64 by default, change amd64 by arm64 for linux on ARM architecture (ex: VM on Apple Silicon)
```

```bash
curl -Lo fission https://github.com/fission/fission/releases/download/v1.19.0/fission-v1.19.0-linux-amd64 \
    && chmod +x fission && sudo mv fission /usr/local/bin/
```

## Step4: Check fission health

```sh
fission version
fission check
```
