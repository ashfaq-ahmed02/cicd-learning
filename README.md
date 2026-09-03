# 🚀 CI/CD Learning

<p align="center">
  <b>🐍 Python • 🧪 Pytest • 🐳 Docker • ⚙️ GitHub Actions • 📦 Docker Hub</b>
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge\&logo=python)

![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED?style=for-the-badge\&logo=docker)

![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-2088FF?style=for-the-badge\&logo=githubactions)

![Pytest](https://img.shields.io/badge/Pytest-Testing-0A9EDC?style=for-the-badge\&logo=pytest)

</p>

---

## 🌟 About

A simple **DevOps & CI/CD learning project** where a Python application is automatically tested, containerized, and pushed to Docker Hub.

### 🔄 Pipeline

```text
💻 Code
   ↓
🔀 GitHub
   ↓
🧪 Pytest
   ↓
🐳 Docker Build
   ↓
📦 Docker Hub
```

---

## 🛠️ Tech Stack

| 🧩 Technology     | 🎯 Purpose       |
| ----------------- | ---------------- |
| 🐍 Python         | Application      |
| 🧪 Pytest         | Testing          |
| 🐳 Docker         | Containerization |
| ⚙️ GitHub Actions | CI/CD            |
| 📦 Docker Hub     | Image Registry   |
| 🔀 Git            | Version Control  |

---

## 📂 Project

```text
cicd-learning/
├── 🐍 app.py
├── 🧪 test_app.py
├── 🐳 Dockerfile
├── ⚙️ .github/workflows/ci.yml
└── 📖 README.md
```

---

## 🧪 Test

```bash
pip install pytest
pytest
```

✅ Automated tests run before the Docker build.

---

## 🐳 Docker

```bash
docker build -t cicd-learning .
docker run --rm cicd-learning
```

Output:

```text
30
```

---

## ⚙️ CI/CD

Every push to `main` triggers:

**GitHub Actions → Test → Docker Build → Docker Hub 🚀**

Docker Image:

```text
ashfaqahmed02/cicd-learning:latest
```

---

## 🎯 What I Learned

✅ Git & GitHub
✅ Automated Testing
✅ Docker
✅ GitHub Actions
✅ CI/CD Pipeline
✅ Docker Hub
✅ DevOps Fundamentals

---

## 🚧 Next Steps

`Jenkins` → `Terraform` → `Cloud` → `Kubernetes` → `Monitoring`

---

## 👨‍💻 Ashfaq Ahmed M

**CSE Student | DevOps & Cloud Learner**

> 🚀 Learn • Build • Automate • Deploy
