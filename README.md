# Ansible Cluster with Docker and Kubernetes

This project demonstrates how to set up an Ansible cluster manually using Docker containers and Kubernetes pods, without relying on pre-built images.

## Project Structure
- `Dockerfile.master`: Dockerfile to build the Ansible Master container.
- `Dockerfile.node`: Dockerfile to build the Ansible Node container.
- `ansible-master.yaml`: Kubernetes manifest to deploy the Ansible Master pod.
- `ansible-node.yaml`: Kubernetes manifest to deploy the Ansible Node pod.

## Usage

1. Build Docker images:
```bash
docker build -t ansible-master -f Dockerfile.master .
docker build -t ansible-node -f Dockerfile.node .
```

2. Load Docker images into Kind (if using Kind):
```bash
kind load docker-image ansible-master
kind load docker-image ansible-node
```

3. Apply Kubernetes manifests:
```bash
kubectl apply -f ansible-master.yaml
kubectl apply -f ansible-node.yaml
```

4. Verify pods are running:
```bash
kubectl get pods
```
