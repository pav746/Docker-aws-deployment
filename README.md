# Docker-aws-deployment
# 🚀 Dockerized Static Website Deployment on AWS EC2

## 📌 Project Overview

This project demonstrates how to containerize a static website using Docker and deploy it on an AWS EC2 instance.

---

## 🛠️ Tech Stack

* Docker
* AWS EC2
* Nginx
* GitHub

---

## ⚙️ Steps Performed

### 1️⃣ Build & Push Docker Image (Local Machine)

```bash
docker buildx create --use
docker buildx inspect --bootstrap
docker buildx build --platform linux/amd64 -t pav746/project:latest --push .
```

---

### 2️⃣ Setup EC2 Instance

```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
```

---

### 3️⃣ Pull and Run Container on EC2

```bash
sudo docker pull pav746/project
sudo docker run -d -p 80:80 pav746/project
```

---

## 🌍 Access Website

Open in browser:

```
http://<your-ec2-public-ip>
```

---

## ⚠️ Challenges Faced

* Faced **Docker architecture mismatch (ARM vs AMD64)**
* Fixed using Docker Buildx with `--platform linux/amd64`

---

## 📸 Screenshots

### 🔹 EC2 Instance

![EC2](screenshots/ec2-instance.png)

### 🔹 Website Live

![Website](screenshots/website-live.png)

### 🔹 Docker Container Running

![Docker](screenshots/docker-ps.png)

---

## 🧠 Key Learnings

* Docker containerization
* Cross-platform image building using Buildx
* Deploying containers on AWS EC2
* Debugging real-world DevOps issues

---

## 🚀 Future Improvements

* Add CI/CD using GitHub Actions
* Attach custom domain
* Enable HTTPS using SSL

---

## 🙌 Conclusion

Successfully deployed a Dockerized static website on AWS EC2 and resolved cross-platform issues, gaining hands-on experience in real-world DevOps practices.
