# 🚀 CI/CD Learning — Python • Docker • GitHub Actions

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,100:2c5364&height=200&section=header&text=CI/CD%20Learning&fontSize=50&fontColor=ffffff&animation=fadeIn&fontAlignY=35" />
</p>

<p align="center">
  <b>🐍 Python</b> •
  <b>🧪 Pytest</b> •
  <b>🐳 Docker</b> •
  <b>⚙️ GitHub Actions</b> •
  <b>📦 Docker Hub</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pytest-Testing-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-Containerization-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker%20Hub-Registry-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
</p>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/ashfaq-ahmed02/cicd-learning?style=flat-square" />
  <img src="https://img.shields.io/github/repo-size/ashfaq-ahmed02/cicd-learning?style=flat-square" />
  <img src="https://img.shields.io/github/license/ashfaq-ahmed02/cicd-learning?style=flat-square" />
</p>

---

## 🌟 About This Project

**CI/CD Learning** is a hands-on DevOps project created to understand how modern software can be **tested, built, containerized, and delivered automatically**.

The project uses a simple Python application to demonstrate a complete beginner-friendly CI/CD workflow using **Git, GitHub, Pytest, Docker, GitHub Actions, and Docker Hub**.

> 💡 **Goal:** Learn DevOps by building and automating a real CI/CD pipeline.

---

## 🔄 CI/CD Pipeline

```text
                 👨‍💻 Developer
                      │
                      ▼
                 🔀 Git Push
                      │
                      ▼
                 🐙 GitHub
                      │
                      ▼
             ⚙️ GitHub Actions
                      │
              ┌───────┴───────┐
              ▼               ▼
         🧪 Pytest        🐳 Docker Build
              │               │
              └───────┬───────┘
                      ▼
                📦 Docker Hub
                      │
                      ▼
                 🚀 Deployment
```

### ✨ Workflow

**Code → Push → Test → Build → Package → Publish**

---

## 🛠️ Tech Stack

| Technology             | Purpose                      |
| ---------------------- | ---------------------------- |
| 🐍 **Python 3.12**     | Application development      |
| 🧪 **Pytest**          | Automated testing            |
| 🐳 **Docker**          | Application containerization |
| ⚙️ **GitHub Actions**  | CI/CD automation             |
| 📦 **Docker Hub**      | Container image registry     |
| 🔀 **Git & GitHub**    | Version control              |
| 🖥️ **Linux / Ubuntu** | DevOps environment           |

---

## 📂 Project Structure

```text
cicd-learning/
│
├── 🐍 app.py
│
├── 🧪 test_app.py
│
├── 🐳 Dockerfile
│
├── ⚙️ .github/
│   └── workflows/
│       └── ci.yml
│
└── 📖 README.md
```

---

## 🐍 Application

The project contains a simple Python application that performs basic operations.

Example:

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

Output:

```text
30
```

---

## 🧪 Automated Testing

Testing is performed using **Pytest**.

### Install Pytest

```bash
pip install pytest
```

### Run Tests

```bash
pytest
```

Example:

```text
================ test session starts ================

test_app.py ....                                    [100%]

================= 4 passed ==========================
```

✅ Tests must pass before the pipeline continues.

---

## 🐳 Docker Containerization

The application is packaged into a Docker image so it can run consistently across different environments.

### Build Image

```bash
docker build -t cicd-learning .
```

### Run Container

```bash
docker run --rm cicd-learning
```

Expected output:

```text
30
```

### Docker Image

```text
ashfaqahmed02/cicd-learning:latest
```

---

## ⚙️ GitHub Actions CI/CD

The project uses **GitHub Actions** to automate the CI/CD workflow.

Whenever code is pushed to the `main` branch:

```text
Git Push
   ↓
GitHub Actions
   ↓
Install Dependencies
   ↓
Run Pytest
   ↓
Build Docker Image
   ↓
Login to Docker Hub
   ↓
Push Docker Image
   ↓
✅ Pipeline Complete
```

### 🔐 Secrets

Docker Hub authentication is handled using GitHub repository secrets instead of exposing credentials inside the workflow.

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

---

## 📦 Docker Hub

The generated Docker image is published to Docker Hub:

```text
ashfaqahmed02/cicd-learning:latest
```

This demonstrates how a CI/CD pipeline can automatically create and publish a container image after successful testing.

---

## 🎯 What I Learned

### 🔀 Version Control

* Git fundamentals
* GitHub repositories
* Branches & commits
* Push & pull workflows

### 🧪 Testing

* Pytest
* Automated test execution
* Test-driven CI workflow

### 🐳 Docker

* Dockerfiles
* Images & containers
* Container execution
* Docker Hub
* Image publishing

### ⚙️ CI/CD

* GitHub Actions
* Workflow configuration
* Automated builds
* Secrets management
* Continuous Integration
* Continuous Delivery

### ☁️ DevOps Fundamentals

* Automation
* Reproducible builds
* Containerization
* CI/CD pipelines
* DevOps workflow

---

## 📈 Learning Journey

```text
🐧 Linux
   ↓
🔀 Git & GitHub
   ↓
🐳 Docker
   ↓
⚙️ GitHub Actions
   ↓
📦 Docker Hub
   ↓
🔨 Jenkins
   ↓
🏗️ Terraform
   ↓
☁️ Cloud
   ↓
☸️ Kubernetes
   ↓
📊 Monitoring
```

---

## 🚧 Next Steps

The next concepts I plan to explore:

* 🔨 Jenkins
* 🏗️ Terraform
* ☁️ AWS / Azure / GCP
* ☸️ Kubernetes
* 📊 Prometheus & Grafana
* 🔐 DevSecOps
* 🚀 Advanced CI/CD

---

## 💡 Why This Project?

This project is part of my **hands-on DevOps learning journey**.

Instead of only learning theory, I am building small projects to understand how development and operations work together.

> **Learn → Build → Automate → Deploy → Improve**

---

## 👨‍💻 About Me

### **Ashfaq Ahmed M**

🎓 **CSE Student**
☁️ **DevOps & Cloud Learner**
💻 **Software Developer**
🔐 **Network Security Enthusiast**

I am currently building my skills in **DevOps, Cloud Computing, CI/CD, Docker, Kubernetes, and Network Security** through hands-on projects.

---

## 📊 Project Goals

```text
              🚀 CI/CD LEARNING
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
   🧪 Testing    🐳 Containers   ⚙️ Automation
       │             │             │
       └─────────────┼─────────────┘
                     ▼
              📦 Reliable Builds
                     │
                     ▼
              🚀 Faster Delivery
```

---

## ⭐ Support

If you found this project useful or you're also learning DevOps:

**⭐ Star this repository**

and follow the journey! 🚀

---

<p align="center">

### 🚀 Learn • Build • Automate • Deploy

**Made with ❤️ by Ashfaq Ahmed M**

</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,100:0f2027&height=120&section=footer" />
</p>
