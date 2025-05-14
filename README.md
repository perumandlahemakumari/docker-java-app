
# 🚀 Docker Java App

This project demonstrates how to containerize a Java application using Docker.  
There are two Docker builds included in this project using two different Dockerfiles: `Dockerfile` and `Dockerfile2`.

---

## ✅ Pre-requisites

- 🐧 Amazon Linux (or similar)
- 🐳 Docker
- 🧬 Git
- ☕ Java 17 (Amazon Corretto)
- 🔨 Maven

---

## 📦 Setup Instructions

### 📌 Step 1: Install Required Packages

```bash
yum install docker -y && systemctl start docker
yum install git -y
yum install java-17-amazon-corretto -y
yum install maven -y
```

### 📌 Step 2: Clone the Project

```bash
git clone https://github.com/perumandlahemakumari/docker-java-app.git
cd docker-java-app
```

### 📌 Step 3: Build the Java App

```bash
mvn clean package
```

---

## 🐳 Docker Build and Run

### 🔹 First Build using `Dockerfile`

```bash
docker build -t javaapp .
docker run -itd --name cont1 -p 8080:8080 javaapp
```

🔗 Visit your app at: `http://<your-ec2-ip>:8080`

### 🔹 Second Build using `Dockerfile2`

To use `Dockerfile2`, rename or specify it directly:

```bash
docker build -t javaapp -f Dockerfile2 .
docker run -itd --name cont2 -p 8080:8080 javaapp
```

---

## 📂 Optional: Apache Tomcat Setup

```bash
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.105/bin/apache-tomcat-9.0.105.tar.gz
tar -xvf apache-tomcat-9.0.105.tar.gz
cp apache-tomcat-9.0.105/conf/tomcat-users.xml .
rm -rf apache-tomcat-9.0.105.tar.gz apache-tomcat-9.0.105
```

---

## 🛠️ Managing Containers

```bash
docker ps              # List containers
docker stop <id>       # Stop container
docker rm <id>         # Remove container
```

---

## 📝 Notes

- 🧱 Use `Dockerfile` for your first build  
- 🧱 Use `Dockerfile2` for the second variation of the build

