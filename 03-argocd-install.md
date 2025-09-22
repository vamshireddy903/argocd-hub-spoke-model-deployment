# Argo CD Setup

## Install Argo CD

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Run Argo CD in HTTP Mode(Insecure)

https://github.com/argoproj/argo-cd/blob/54f1572d46d8d611018f4854cf2f24a24a3ac088/docs/operator-manual/argocd-cmd-params-cm.yaml#L82

## Expose Argo CD Server Service in NodePort Mode

```
kubectl edit svc argocd-server -n argocd
```

and change the type to NodePort from ClusterIP


# 1. Download the Latest CLI Release

You can use curl to download the latest Argo CD CLI binary:

# Download the latest Argo CD CLI
```
VERSION=$(curl -s https://api.github.com/repos/argoproj/argo-cd/releases/latest | grep tag_name | cut -d '"' -f 4)
curl -sSL -o argocd https://github.com/argoproj/argo-cd/releases/download/${VERSION}/argocd-linux-amd64
```
2. Make the Binary Executable

       chmod +x argocd

3. Move it to a Directory in Your PATH

       sudo mv argocd /usr/local/bin/

4. Verify Installation

       argocd version


You should see output like:

argocd: v2.x.x

**NOTE:** Make sure you have curl installed: sudo apt update && sudo apt install curl -y

for more info: https://argo-cd.readthedocs.io/en/stable/cli_installation/
