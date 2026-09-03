# 🚀 CI/CD Learning — Python + Docker + GitHub Actions

<p align="center">
  <b>A hands-on CI/CD learning project built from the ground up.</b><br>
  Python Testing → Docker → GitHub Actions → Docker Hub
</p>

<p align="center">

<img src="https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">

<img src="https://img.shields.io/badge/Docker-Containerization-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker">

<img src="https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions">

<img src="https://img.shields.io/badge/Pytest-Testing-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="Pytest">

</p>

---

## 📌 About This Project

This repository is a practical **CI/CD learning project** created to understand how modern DevOps pipelines work.

The project starts with a simple Python application and automatically:

```text
Write Code
    ↓
Push to GitHub
    ↓
Run Automated Tests
    ↓
Build Docker Image
    ↓
Push Image to Docker Hub
```

The main goal is to understand the complete workflow instead of learning CI/CD tools individually.

---

## 🔄 CI/CD Pipeline

```text
                    ┌─────────────────┐
                    │    Developer    │
                    └────────┬────────┘
                             │
                             │ git push
                             ▼
                    ┌─────────────────┐
                    │     GitHub      │
                    │   Repository    │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ GitHub Actions  │
                    └────────┬────────┘
                             │
                 ┌───────────▼───────────┐
                 │       TEST JOB        │
                 │                       │
                 │ Checkout Code         │
                 │ Setup Python 3.12     │
                 │ Install Pytest        │
                 │ Run Tests             │
                 └───────────┬───────────┘
                             │
                       Tests Passed
                             │
                             ▼
                 ┌───────────────────────┐
                 │      DOCKER JOB       │
                 │                       │
                 │ Login to Docker Hub   │
                 │ Build Docker Image    │
                 │ Push Docker Image     │
                 └───────────┬───────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │   Docker Hub    │
                    │ Container Image │
                    └─────────────────┘
```

---

## 🛠️ Tech Stack

| Technology        | Purpose                      |
| ----------------- | ---------------------------- |
| 🐍 Python 3.12    | Application development      |
| 🧪 Pytest         | Automated testing            |
| 🐳 Docker         | Application containerization |
| ⚙️ GitHub Actions | CI/CD automation             |
| 📦 Docker Hub     | Container image registry     |
| 🔀 Git            | Version control              |
| 🌐 GitHub         | Source code management       |
| 🐧 Linux / Ubuntu | DevOps learning environment  |

---

## 📂 Project Structure

```text
cicd-learning/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── app.py
├── test_app.py
├── Dockerfile
└── README.md
```

### File Explanation

| File          | Description                                |
| ------------- | ------------------------------------------ |
| `app.py`      | Main Python application                    |
| `test_app.py` | Automated Pytest test                      |
| `Dockerfile`  | Instructions for building the Docker image |
| `ci.yml`      | GitHub Actions CI/CD pipeline              |
| `README.md`   | Project documentation                      |

---

# 🐍 Python Application

The application contains a simple addition function.

```python
def add(a, b):
    return a + b

print(add(10, 20))
```

### Output

```text
30
```

---

# 🧪 Automated Testing

The project uses **Pytest** to automatically verify the application.

```python
from app import add

def test_add():
    assert add(10, 20) == 30
```

### Run Tests Locally

Install Pytest:

```bash
pip install pytest
```

Run the tests:

```bash
pytest
```

Expected result:

```text
1 passed
```

---

# 🐳 Docker

The application is containerized using Docker.

The project uses:

```dockerfile
FROM python:3.12-slim

WORKDIR /app

COPY app.py .
COPY test_app.py .

RUN pip install pytest

CMD ["python", "app.py"]
```

---

## 🔨 Build Docker Image

```bash
docker build -t cicd-learning .
```

Check the image:

```bash
docker images
```

---

## ▶️ Run Docker Container

```bash
docker run --rm cicd-learning
```

Expected output:

```text
30
```

---

## 🧪 Run Tests Inside Docker

```bash
docker run --rm cicd-learning pytest
```

Expected result:

```text
1 passed
```

---

# ⚙️ GitHub Actions

The CI/CD workflow is located at:

```text
.github/workflows/ci.yml
```

The pipeline is triggered whenever code is pushed to the `main` branch.

```yaml
on:
  push:
    branches:
      - main
```

---

## 🔹 Stage 1 — Continuous Integration

The first job performs automated testing.

### Pipeline steps

```text
Checkout Code
      ↓
Setup Python 3.12
      ↓
Install Pytest
      ↓
Run Tests
```

If the tests fail:

```text
❌ Tests Failed
      ↓
Pipeline Stops
```

If the tests pass:

```text
✅ Tests Passed
      ↓
Docker Job Starts
```

---

# 🐳 Stage 2 — Docker Build & Push

The Docker job depends on the test job:

```yaml
docker:
  needs: test
```

This means Docker will only be built after the tests successfully pass.

The pipeline then:

```text
Login to Docker Hub
       ↓
Build Docker Image
       ↓
Push Docker Image
```

---

# 🔐 GitHub Actions Secrets

Docker Hub credentials should **never be hard-coded** inside the workflow.

The pipeline uses GitHub Secrets:

```text
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
```

Configure them from:

```text
GitHub
  ↓
Repository
  ↓
Settings
  ↓
Secrets and variables
  ↓
Actions
```

> ⚠️ Never commit passwords, access tokens, API keys, or other sensitive credentials to GitHub.

---

# 📦 Docker Hub Image

The CI/CD pipeline builds and pushes the Docker image:

```text
ashfaqahmed02/cicd-learning:latest
```

This demonstrates how a CI/CD pipeline can automatically package an application and publish it to a container registry.

---

# 🔁 Complete Workflow

Whenever I make a change:

```bash
git add .
git commit -m "Update application"
git push origin main
```

GitHub Actions automatically starts:

```text
Git Push
   ↓
GitHub Actions
   ↓
Checkout
   ↓
Python Setup
   ↓
Install Pytest
   ↓
Run Tests
   ↓
Tests Passed?
   │
   ├── ❌ NO → Stop Pipeline
   │
   └── ✅ YES
          ↓
      Docker Build
          ↓
      Docker Login
          ↓
      Docker Push
          ↓
      Docker Hub
```

---

# 🎯 What I Learned

Through this project, I learned the fundamentals of:

### Git & GitHub

* Git repository management
* Branches
* Commits
* Push and pull
* GitHub repository workflow

### Testing

* Writing unit tests
* Using Pytest
* Automated test execution
* Test-driven CI validation

### Docker

* Dockerfiles
* Docker images
* Docker containers
* Image building
* Running containers
* Docker Hub

### CI/CD

* Continuous Integration
* Continuous Delivery concepts
* GitHub Actions
* Workflow YAML
* Jobs and steps
* Job dependencies
* Automated testing
* Automated Docker builds
* Automated Docker image publishing

### DevOps

```text
Code
 ↓
Version Control
 ↓
Testing
 ↓
Containerization
 ↓
Automation
 ↓
Container Registry
```

---

# 🚧 Future Improvements

This project will be expanded as part of my DevOps learning journey.

* [ ] Add more Python unit tests
* [ ] Add code quality checks with Ruff
* [ ] Add Docker image version tags
* [ ] Add Docker Compose
* [ ] Add environment variables
* [ ] Add Kubernetes deployment
* [ ] Add Jenkins CI/CD pipeline
* [ ] Add Terraform infrastructure
* [ ] Deploy application to AWS / Azure / GCP
* [ ] Add monitoring and logging
* [ ] Add CI/CD notifications
* [ ] Add development and production environments

---

# 🧠 My DevOps Learning Journey

This repository is part of my journey toward becoming a **DevOps / Cloud Engineer**.

My current learning path:

```text
Linux
  ↓
Git & GitHub
  ↓
Docker
  ↓
CI/CD
  ↓
GitHub Actions
  ↓
Jenkins
  ↓
Terraform
  ↓
Cloud
  ↓
Kubernetes
  ↓
Monitoring
```

The focus is on **learning by building real projects** and understanding how different DevOps tools work together.

---

# 🚀 CI/CD Philosophy

> **Build it. Test it. Containerize it. Automate it. Deploy it.**

The goal of this repository is not just to make a pipeline work, but to understand **why each stage exists and how it contributes to reliable software delivery.**

---

## 👨‍💻 Author

### Ashfaq Ahmed M

**Computer Science & Engineering Student**
**DevOps | Cloud | CI/CD | Python | Docker**

<p align="center">

<i>Learning • Building • Automating • Improving 🚀</i>

</p>

---

<p align="center">
  ⭐ If this repository helped you understand CI/CD, feel free to star it!
</p>
