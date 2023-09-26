# terraform_Kubernetes
-----------------------
![image](https://github.com/chithu123/terraform_Kubernetes/assets/99309914/0bc37647-f91a-46f0-b085-5581104c5df1)

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


# terraform_Docker
--------------------

![image](https://github.com/chithu123/terraform_Kubernetes/assets/99309914/193aa6f7-9f2c-483b-a5cc-64b6db8e8d09)


We will implement a simple LAMP stack using terraform and docker.

The requirements in detail:

Install terraform binary version=1.1.5 on iac-server
The Docker provider has already been configured using the kreuzwerker/docker provider. Check out the provider. tf given at /root/code/terraform-challenges/challenge2
Create a terraform resource named php-httpd-image for building a docker image with the following specifications:
Image name: php-httpd: challenge
Build context: lamp_stack/php_httpd
Labels: challenge: second
Create a terraform resource named mariadb-image for building a docker image with the following specifications:
Image name: mariadb: challenge
Build context: lamp_stack/custom_db
Labels: challenge: second
Define a terraform resource php-httpd for creating a docker container with the following specifications:
Container Name: webserver
Hostname: php-httpd
Image used: php-httpd: challenge
Attach the container to the network my_network
Publish a container’s port(s) to the host:
Host port: 0.0.0.0:80
containerPort: 80
Labels: challenge: second
Create a volume with host_path /root/code/terraform-challenges/challenge2/lamp_stack/website_content/ and container_path /var/www/html within the webserver container.
Define a terraform resource phpmyadmin for docker container with the following configurations
Container Name: db_dashboard
Image Used: phpmyadmin/phpmyadmin
Attach the container to the network my_network
Publish a container’s port(s) to the host:
Host port: 0.0.0.0:8081
containerPort: 80
Labels: challenge: second
Establish link-based connectivity between db and db_dashboard containers (Deprecated)
Explicitly specify a dependency on mariadb terraform resource
Define a terraform resource mariadb for docker container with the following configurations:
Image Used: mariadb: challenge
Attach the container to the network my_network
Publish a container’s port(s) to the host:
Hostport: 0.0.0.0:3306
containerPort: 3306
Labels: challenge: second
Define environment variables inside mariadb resource:
MYSQL_ROOT_PASSWORD=1234
MYSQL_DATABASE=simple-website
Attach volume mariadb-volume to /var/lib/mysql a directory within db container.





