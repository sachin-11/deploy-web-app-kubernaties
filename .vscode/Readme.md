# Setting Up a Kubernetes Cluster with Minikube and kubectl

This guide provides step-by-step instructions on setting up a Kubernetes cluster locally using Minikube and managing it using the `kubectl` command-line tool. This is a simplified setup for development and testing purposes.

## Prerequisites

Before you begin, ensure that you have the following prerequisites installed:

- Homebrew (for macOS) or equivalent package manager for other platforms.
- `kubectl`: The Kubernetes command-line tool.
- `minikube`: A tool to run a single-node Kubernetes cluster.

### Installing kubectl and minikube (macOS)

To install `kubectl` and `minikube` on macOS using Homebrew, run the following commands:

```bash
brew install kubectl
brew install minikube

minikube start

kubectl get node -o wide
kubectl apply -f mongo-config.yaml
kubectl apply -f secret.yaml
kubectl apply -f mongo-app.yam
kubectl apply -f web-app.yaml
kubectl get pod
kubectl expose deployment <your-web-app-deployment-name> --type=NodePort --port=80
minikube service <your-web-app-service-name>
kubectl delete deployment --all
Delete all secrets:

kubectl delete secret --all
Cleaning Up
To stop and delete the Minikube cluster, you can use the following command:

minikube delete
