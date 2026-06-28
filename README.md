Project Overview

This project shows a complete automated CI/CD pipeline for a containerized React application deployed on an Amazon Linux EC2 instance. It includes infrastructure setup, multi-branch pipeline logic, and monitoring.


Architecture Components

•	Version Control: GitHub (with separate dev and main branches) 
•	Automation: Jenkins (Multibranch Pipeline) 
•	Containerization: Docker & Docker Compose 
•	Infrastructure: AWS EC2 (Amazon Linux) 
•	Monitoring: Prometheus & Grafana (with Discord alerts)

Phase-by-Phase Documentation:

Phase 1: Environment Setup & Dockerization

•	Installed Git, Docker, and Docker Compose on an Amazon Linux EC2 instance. 
•	Created a Dockerfile using a single-stage Nginx build to serve the pre-built React application. 
•	Created a docker-compose.yml file to manage the container on the EC2 instance. 
•	Created build.sh and deploy.sh scripts to automate the build and deployment process. 

Phase 2: CI/CD Pipeline (Jenkins)

•	Created a Jenkinsfile with branch-based pipeline logic: 
o	dev branch: Automatically builds the Docker image and pushes it to a public Docker Hub repository. 
o	main branch: Automatically builds the Docker image and pushes it to a private Docker Hub repository using API-based automation. 
•	The pipeline runs the deploy.sh script, which removes the old container (if it exists) and starts the new container.

Phase 3: Monitoring & Alerts

•	Installed Prometheus as a systemd service. 
•	Installed Grafana using Yum. 
•	Configured Grafana to send alerts to a Discord channel if the application or server goes down.

Screenshots:

AWS EC2
<img width="950" height="510" alt="Instance Public Ip" src="https://github.com/user-attachments/assets/b99bd474-aaa4-42f8-9550-0cdc324ac8ad" />

EC2 Security Groups 
<img width="955" height="509" alt="EC2 security groups" src="https://github.com/user-attachments/assets/50cf080e-c709-4b04-82e2-7a536d085ad3" />

EC2 ssh connection with Gitbash
<img width="959" height="542" alt="Ec2 ssh connection via gitbash" src="https://github.com/user-attachments/assets/ca81164c-9cdd-4154-9266-8896626b0aa3" />

Live Application
<img width="958" height="539" alt="Website access via public ip" src="https://github.com/user-attachments/assets/88639f10-0b1b-4c54-aca2-d2613d139d10" />

Docker Hub
<img width="955" height="512" alt="Docker hub repos" src="https://github.com/user-attachments/assets/89dd8f33-c42a-4b15-af2b-a08feb66ab7d" />
<img width="953" height="508" alt="dockerhub 2" src="https://github.com/user-attachments/assets/5209d8d5-157c-4cc5-8865-7fb0095a2dbd" />

Jenkins
Junkins Dashboard:
<img width="950" height="509" alt="Jenkins dashboard" src="https://github.com/user-attachments/assets/1859107a-1ffe-4b97-b30d-f37570b9e59b" />

Multistage Pipeline
<img width="953" height="476" alt="Jenkins multibranch pipeline" src="https://github.com/user-attachments/assets/8722de20-5c15-4692-9872-2a43099b34d2" />

Jenkins Dev Deployment
<img width="956" height="514" alt="Jenkins Dev" src="https://github.com/user-attachments/assets/8743ab32-2d8a-47b9-afbf-a3e1f7705280" />
<img width="956" height="512" alt="jenkins dev stages" src="https://github.com/user-attachments/assets/72b8a6c6-dad0-4256-93e3-a4f59e8b7ac8" />
<img width="944" height="505" alt="jenkins dev console output" src="https://github.com/user-attachments/assets/8d847143-ad27-4552-b836-31978bce1270" />

Jenkins Main Deployment



















