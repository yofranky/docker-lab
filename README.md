# Docker Lab

A hands-on lab for experimenting with containerized services, CI/CD pipelines, and infrastructure automation.  
This repository is a sandbox for building, testing, and deploying using Docker, GitHub Actions, and related tooling.

---

## 📂 Project Structure

. 
├── .github/workflows/pipeline.yml # GitHub Actions CI/CD workflow 
├── ci_cd/ # Dockerfiles for CI/CD and lab environment 
│ ├── Dockerfile 
│ └── Dockerfile-old.txt 
├── networking/ # Networking-related experiments 
├── terraform/ # Infrastructure as Code (Terraform configs) 
└── webserver/ # Simple web server container 
├── Dockerfile 
└── index.html


---

## 🚀 Getting Started

### 1. Clone the repo
```bash
git clone git@github.com:yofranky/docker-lab.git
cd docker-lab
