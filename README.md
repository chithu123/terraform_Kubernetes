# terraform_Kubernetes

Utilize /root/terraform_challenge a directory to store your Terraform configuration files.

The requirements in detail:

Terraform version: 1.1.5 installed on controlplane?
Configure terraform and provider settings within the provider.tf file with the following specifications:
Configure terraform to use hashicorp/kubernetes provider.
Specify the provider’s local name: kubernetes
Provider version: 2.11.0
Configure Kubernetes provider with the path to your kubeconfig file: /root/.kube/config
Create a terraform resource frontend for Kubernetes deployment with the following specs:
Deployment Name: frontend
Deployment Labels = name: frontend
Replicas: 4
Pod Labels = name: webapp
Image: kodekloud/webapp-color:v1
Container name: simple-webapp
Container port: 8080
Create a terraform resource webapp-service for Kubernetes service with the following specs:
Service name: webapp-service
Service Type: NodePort
Port: 8080
NodePort: 30080
