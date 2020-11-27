# K8S on Okteto with GitHub Actions

Build the Docker Image, Publish on Dockerhub and Deploy on Okteto.

## Base 64 Config okteto-kube.conf

```bash
cat okteto-kube.config | base64
```
Complete the Secret's Tab on GitHub with Dockerhub Username & Passowrd and Kube Config.

## Secret's

<p align="center">
<img src="screenshots/Okteto.jpg" width="600" >
</p>

## Running

<p align="center">
<img src="screenshots/Actions.jpg" width="600" >
</p>

## Important

It is important that we generate the first deployment manually, with this command, so that GitHub Actions do not fail.

```bash
export KUBECONFIG=$HOME/Downloads/okteto-kube.config:${KUBECONFIG:-$HOME/.kube/config}

kubectl apply -f ./deployment/deployment.yaml
```

## Checking the Cluster

The first command I retrieve the pods from the deployment. Then I make the queries, via curl, to the EndPoint of the Cluster in Okteto to check the balance.

<p align="center">
<img src="screenshots/Kubectl.jpg" width="600" >
</p>

The Website

<p align="center">
<img src="screenshots/Website.png" width="600" >
</p>