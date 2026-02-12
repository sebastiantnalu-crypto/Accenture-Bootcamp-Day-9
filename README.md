Kubernetes Deployment Documentation

Project Name: Nginx Deployment with ConfigMap & Secret
Environment: AWS EC2 (Ubuntu)
Author: Sebastian Tomichan Naluthengumgal

1. Objective
The objective of this task was to:
•	Deploy an Nginx application in Kubernetes
•	Use a ConfigMap to store configuration data
•	Use a Secret to store sensitive information
•	Expose the application using a Kubernetes Service
•	Access the application via browser using port forwarding

3. Environment Setup
•	OS: Ubuntu (EC2 instance)
•	Kubernetes installed and configured
•	kubectl CLI configured
•	Working directory: ~/sebastian-k8s

3.Core Concepts
Question	One-Line Answer
What is Kubernetes?	Kubernetes is a container orchestration platform that automates deployment, scaling, and management of containerized applications.
What are containers?	Containers are lightweight, portable packages that include an application and all its dependencies to run consistently anywhere.
What is kube-system?	kube-system is a special Kubernetes namespace that contains core system components required for the cluster to function.

4.Kubernetes Core Components
Component	One-Line Explanation
etcd	A distributed key-value database that stores all Kubernetes cluster state and configuration data.
API Server	The central component that receives and processes all Kubernetes requests and updates etcd.
Scheduler	Decides which worker node a new pod should run on based on resources and policies.
Controllers	Background processes that ensure the actual cluster state matches the desired state.

5.Kubernetes Commands
Command	One-Line Explanation
kubectl get pods	Lists all pods in the default namespace.
kubectl get pods -n kube-system	Lists all pods in the kube-system namespace (system components).
kubectl describe pod etcd-minikube -n kube-system	Shows detailed information about the etcd-minikube pod in kube-system.
kubectl run mahendra-nginx --image=nginx	Creates and runs a pod named mahendra-nginx using the Nginx image.
kubectl exec -it mahendra-nginx -- /bin/bash	Opens an interactive Bash shell inside the mahendra-nginx pod.
kubectl delete pod Mahendra-nginx	Deletes the specified pod.
kubectl create deployment mahendra-nginx --image=nginx	Creates a deployment running Nginx containers.
kubectl delete pod mahendra-nginx-6889bb9b-tbjkj	Deletes a specific pod (it will be recreated if managed by a deployment).
kubectl delete deployment Mahendra-nginx	Deletes the deployment and all pods it manages.
kubectl scale deployment mahendra-nginx --replicas=5	Scales the deployment to run 5 pod replicas.

6.Teste 
Both ngnix and apache server deployment
 
7. Kubernetes Resources Created
Four YAML configuration files were created:
•	configmap.yaml
•	secret.yaml
•	deployment.yaml
•	service.yaml

9. ConfigMap Configuration
•	File: configmap.yaml, secret.yaml, deployment.yaml, and service.yaml
•	Purpose: Store non-sensitive configuration data.
 
And I created by using this commands:

•	kubectl apply -f configmap.yaml
•	kubectl apply -f secret.yaml
•	kubectl apply -f deployment.yaml
•	kubectl apply -f service.yaml

Then i verify everthing
•	kubectl get pods
•	kubectl get svc

Forward
•	kubectl port-forward service/nginx-service 9090:80 --address 0.0.0.0
 

In wed I used to check connection “51.21.201.13:9090”
 
environment variables inside the running pod
 


My documentation link : https://drive.google.com/file/d/1tukJ4bRo3gtEvEMwBSpgr4ydOp9VT9eM/view?usp=sharing
