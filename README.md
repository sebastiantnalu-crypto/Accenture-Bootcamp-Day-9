# Kubernetes Deployment Documentation
Welcome to the **Nginx Deployment** project repository. This project demonstrates how to deploy a containerized Nginx application on an AWS-managed Kubernetes environment using core K8s objects like ConfigMaps, Secrets, and Services.
## 🚀 Project Overview
 * **Project Name:** Nginx Deployment with ConfigMap & Secret
 * **Author:** Sebastian Tomichan Naluthengumgal
 * **Environment:** AWS EC2 (Ubuntu)
 * **Objective:**
   * Deploy an Nginx application in Kubernetes.
   * Manage configuration via **ConfigMaps**.
   * Secure sensitive data using **Secrets**.
   * Expose the application via a **Kubernetes Service**.
   * Access the app through **Port Forwarding**.
## 🛠 Environment Setup
 * **OS:** Ubuntu (EC2 Instance)
 * **Tools:** Kubernetes, kubectl CLI
 * **Working Directory:** ~/sebastian-k8s
## 🧠 Core Concepts
### 1. Fundamentals
| Question | One-Line Answer |
|---|---|
| **What is Kubernetes?** | A container orchestration platform that automates deployment, scaling, and management of apps. |
| **What are containers?** | Lightweight, portable packages including an application and all its dependencies. |
| **What is kube-system?** | A namespace for core system components required for the cluster to function. |
### 2. Control Plane Components
| Component | One-Line Explanation |
|---|---|
| **etcd** | A distributed key-value database storing all cluster state and configuration. |
| **API Server** | The central gateway that processes all Kubernetes requests and updates etcd. |
| **Scheduler** | Assigns pods to worker nodes based on resource availability and policies. |
| **Controllers** | Processes that ensure the actual cluster state matches the desired state. |
## 💻 Essential Commands Reference
| Command | Purpose |
|---|---|
| kubectl get pods | Lists pods in the default namespace. |
| kubectl get pods -n kube-system | Lists core system component pods. |
| kubectl run [name] --image=nginx | Runs a standalone pod using the Nginx image. |
| kubectl exec -it [name] -- /bin/bash | Opens an interactive shell inside a pod. |
| kubectl create deployment [name] | Creates a managed deployment. |
| kubectl scale deployment [name] --replicas=5 | Scales the application to 5 replicas. |
| kubectl delete deployment [name] | Deletes the deployment and its associated pods. |
## 🏗 Implementation Details
### Resources Created
The following YAML files define the application stack:
 * configmap.yaml: Stores non-sensitive configuration data.
 * secret.yaml: Stores sensitive information (encoded).
 * deployment.yaml: Defines the Nginx container and pulls from ConfigMap/Secret.
 * service.yaml: Defines how the application is accessed internally.
### Deployment Steps
```bash
# 1. Apply configuration and secrets
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml

# 2. Deploy the application and service
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

# 3. Verify resources
kubectl get pods
kubectl get svc

```
## 🌐 Accessing the Application
To access the Nginx server from your browser, use **Port Forwarding**:
```bash
kubectl port-forward service/nginx-service 9090:80 --address 0.0.0.0

```
> **Access URL:** http://51.21.201.13:9090
> 
## 🔗 Documentation
 * **Project Link:** [[Insert Link Here]](https://drive.google.com/file/d/1tukJ4bRo3gtEvEMwBSpgr4ydOp9VT9eM/view?usp=sharing)
```

```
 
