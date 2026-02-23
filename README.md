# TrendStoreProject
Project Description
This project demonstrates a complete end-to-end DevOps pipeline where a React application is:
•	Containerized using Docker
•	Pushed to DockerHub
•	Deployed to AWS EKS
•	Automated via Jenkins CI/CD
•	Provisioned using Terraform
•	Monitored using AWS CloudWatch
Architecture Flow
Developer → GitHub → Jenkins → Docker → DockerHub → EKS → LoadBalancer → End Users
Infrastructure Provisioned (Terraform)
Using Terraform:
•	VPC
•	Public Subnets
•	IAM Roles
•	EC2 (Jenkins Server)
•	EKS Cluster
•	Worker Nodes
Commands Used:
•	terraform init
•	terraform plan
•	terraform apply
Docker Implementation
Dockerfile created to serve React app on port 3000.
http:// http://13.126.164.133:3000
Build Image:
docker build -t poov23/trend-app:latest .
Push to DockerHub:
docker push poov23/trend-app:latest
DockerHub Repo:
https://hub.docker.com/r/poov23/trend-app
Kubernetes Deployment (EKS)
Deployment and Service YAML created.
Deploy:
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
Verify:
kubectl get pods
kubectl get svc
Application URL
Application exposed via LoadBalancer:
http:// a0c3eacc5175546839bc808dea2545fe-297781735.ap-south-1.elb.amazonaws.com
Jenkins CI/CD Pipeline
Pipeline Stages:
1.	Clone GitHub Repository
2.	Build Docker Image
3.	Push Image to DockerHub
4.	Deploy to EKS using kubectl
GitHub Webhook configured for automatic build trigger on every commit.
Monitoring
Monitoring implemented using AWS CloudWatch.
Monitored Metrics:
•	Node CPU & Memory
•	Pod Health
•	Network Usage
•	Application Availability
