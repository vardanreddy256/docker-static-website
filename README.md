# Docker Static Website with CI/CD Pipeline

This project demonstrates how to deploy a static website using **Docker and Nginx** and automate the deployment using a **Jenkins CI/CD pipeline**.

The application is containerized using Docker and automatically built and deployed using Jenkins whenever code changes are pushed to GitHub.

---

# Technologies Used

- Docker
- Nginx
- Jenkins
- Git
- GitHub
- Linux (Ubuntu)

---

# Project Structure

docker-static-website

├── Dockerfile  
├── index.html  
├── Jenkinsfile  
└── README.md

---

# Build Docker Image

Run the following command to build the Docker image:


docker build -t mywebsite .


---

# Run Docker Container

Start the container using:


docker run -d -p 8090:80 --name mywebsite-container mywebsite


---

# Access the Website

Open your browser and visit:


http://localhost:8090


---

# Jenkins CI/CD Pipeline

This project includes a Jenkins pipeline that automates the deployment process.

The pipeline performs the following steps:

1. Pulls the latest code from GitHub
2. Builds the Docker image
3. Stops the existing container if it exists
4. Deploys a new container

---

# Jenkins Pipeline Workflow


Developer Push Code
↓
GitHub
↓
Jenkins
↓
Build Docker Image
↓
Stop Old Container
↓
Run New Container
↓
Website Updated


---

# Jenkins Pipeline Stages

- Build Docker Image
- Stop Old Container
- Deploy Container

---

# Example Jenkinsfile


pipeline {
agent any

stages {

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t mywebsite .'
        }
    }

    stage('Stop Old Container') {
        steps {
            sh 'docker stop mywebsite-container || true'
            sh 'docker rm mywebsite-container || true'
        }
    }

    stage('Deploy Container') {
        steps {
            sh 'docker run -d -p 8090:80 --name mywebsite-container mywebsite'
        }
    }

}

}


---

# Result

Whenever code is pushed to GitHub, Jenkins automatically:

- Fetches the latest code
- Builds a new Docker image
- Stops the old container
- Deploys the updated container

This demonstrates a **basic CI/CD pipeline using Jenkins and Docker**.

---

# Author

DEVALAPALLI YASOVARDHAN REDDY  

DevOps Learning Project
