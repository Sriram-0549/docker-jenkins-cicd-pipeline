# 🚀 Docker Jenkins CI/CD Pipeline

A production-ready CI/CD pipeline built using **Node.js, Docker, Jenkins, GitHub, Docker Hub, and AWS EC2**.

This project demonstrates how every code change pushed to GitHub is automatically built, containerized, pushed to Docker Hub, and deployed on an AWS EC2 instance using Jenkins.

---

## 📌 Features

- ✅ Node.js Express Application
- ✅ Dockerized Application
- ✅ Jenkins Declarative Pipeline
- ✅ GitHub Webhook Integration
- ✅ Automatic Docker Image Build
- ✅ Automatic Docker Hub Push
- ✅ Automatic Deployment to EC2
- ✅ Live Application Access

---

## 🛠️ Technologies Used

- Linux (Ubuntu)
- AWS EC2
- Node.js
- Express.js
- Docker
- Jenkins
- Git
- GitHub
- Docker Hub

---

## 📁 Project Structure

```text
docker-jenkins-cicd-pipeline/
│
├── app.js
├── Dockerfile
├── Jenkinsfile
├── package.json
├── package-lock.json
├── public/
│   └── index.html
├── .gitignore
└── README.md
```

---

## ⚙️ CI/CD Workflow

```text
Developer
      │
git push
      │
      ▼
GitHub Repository
      │
GitHub Webhook
      │
      ▼
Jenkins Pipeline
      │
Checkout Source Code
      │
Build Docker Image
      │
Docker Login
      │
Push Image to Docker Hub
      │
Deploy Container
      │
Application Live on AWS EC2
```

---

## 🚀 How to Run

Clone the repository

```bash
git clone https://github.com/Sriram-0549/docker-jenkins-cicd-pipeline.git
```

Go inside the project

```bash
cd docker-jenkins-cicd-pipeline
```

Install dependencies

```bash
npm install
```

Run the application

```bash
npm start
```

Build Docker Image

```bash
docker build -t node-cicd .
```

Run Docker Container

```bash
docker run -d -p 3000:3000 node-cicd
```

---

## 📷 Screenshots

- Jenkins Pipeline ✅
- Docker Hub Repository ✅
- Live Application ✅

*(Screenshots will be added soon.)*

---

## 👨‍💻 Author

**Sriram C J**

- GitHub: https://github.com/Sriram-0549

---

## ⭐ Future Improvements

- Kubernetes Deployment
- Prometheus Monitoring
- Grafana Dashboard
- ArgoCD GitOps
- Multi-stage Docker Build
