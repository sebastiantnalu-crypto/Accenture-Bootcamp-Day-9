To paste this into GitHub so it renders correctly, copy the code block below. I’ve cleaned up the structure to ensure the tables and code snippets look professional in a README.md file.
```markdown
# Kubernetes Deployment Documentation

## 📝 Project Details
* **Project Name:** Nginx Deployment with ConfigMap & Secret
* **Environment:** AWS EC2 (Ubuntu)
* **Author:** Sebastian Tomichan Naluthengumgal

---

## 🎯 Objective
The objective of this task was to:
* Deploy an **Nginx** application in Kubernetes.
* Use a **ConfigMap** to store configuration data.
* Use a **Secret** to store sensitive information.
* Expose the application using a **Kubernetes Service**.
* Access the application via browser using **Port Forwarding**.

---

## ⚙️ Environment Setup
* **OS:** Ubuntu (EC2 instance)
* **Kubernetes:** Installed and configured
* **CLI:** `kubectl` configured
* **Working Directory:** `~/sebastian-k8s`

---

## 💡 Core Concepts

| Question | One-Line Answer |
| :--- | :--- |
| **What is Kubernetes?** | A container orchestration platform that automates deployment, scaling, and management of containerized applications. |
| **What are containers?** | Lightweight, portable packages that include an application and all its dependencies to run consistently anywhere. |
| **What is kube-system?** | A special Kubernetes namespace that contains core system components required for the cluster to function. |

### Kubernetes Control Plane
| Component | One-Line Explanation |
| :--- | :--- |
| **etcd** | A distributed key-value database that stores all Kubernetes cluster state and configuration data. |
| **API Server** | The central component that receives and processes all Kubernetes requests and updates etcd. |
| **Scheduler** | Decides which worker node a new pod should run on based on resources and policies. |
| **Controllers** | Background processes that ensure the actual cluster state matches the desired state. |

---

## 🛠 Kubernetes Commands Reference

| Command | Explanation |
| :--- | :--- |
| `kubectl get pods` | Lists all pods in the default namespace. |
| `kubectl get pods -n kube-system` | Lists all pods in the kube-system namespace. |
| `kubectl describe pod [name] -n [ns]` | Shows detailed information about a specific pod. |
| `kubectl run [name] --image=nginx` | Creates and runs a standalone Nginx pod. |
| `kubectl exec -it [name] -- /bin/bash` | Opens an interactive Bash shell inside a pod. |
| `kubectl create deployment [name] --image=nginx` | Creates a deployment managing Nginx containers. |
| `kubectl scale deployment [name] --replicas=5` | Scales the deployment to run 5 pod replicas. |
| `kubectl delete deployment [name]` | Deletes the deployment and all managed pods. |

---

## 🚀 Deployment Process

### 1. Resources Created
Four YAML configuration files were developed:
* `configmap.yaml` (Non-sensitive config)
* `secret.yaml` (Sensitive information)
* `deployment.yaml` (Pod & Container specs)
* `service.yaml` (Network exposure)

### 2. Execution
Apply the configurations in the following order:

```bash
kubectl apply -f configmap.yaml
kubectl apply -f secret.yaml
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

```
### 3. Verification
Verify that the pods are running and the service is active:
```bash
kubectl get pods
kubectl get svc

```
## 🌐 Accessing the Application
To expose the application to the internet/local browser from the EC2 instance, use **Port Forwarding**:
```bash
kubectl port-forward service/nginx-service 9090:80 --address 0.0.0.0

```
**Connection Test:**
Open your browser and navigate to:
http://51.21.201.13:9090
## 🔗 Resources
 * **Documentation Link:** [[Insert Link Here](https://drive.google.com/file/d/1tukJ4bRo3gtEvEMwBSpgr4ydOp9VT9eM/view?usp=sharing
)]
```

```
 
