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





