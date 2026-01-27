
# 🌊 Containerization with Docker — From Zero to Practical

---

## 1️⃣ What is Containerization?

### Simple definition

**Containerization** is the process of **packing your application together with everything it needs to run** into one unit called a **container**.

This package includes:

- ✅ Code
    
- ✅ Dependencies (libraries, frameworks)
    
- ✅ Configurations
    
- ✅ Runtime environment
    

📦 → One box. Run it anywhere.

---

### Why was containerization needed?

Before containers:

- “It works on my laptop 😭”
    
- App fails on server due to:
    
    - Different OS
        
    - Different library versions
        
    - Missing dependencies
        

Containerization solves this by saying:

> “Run the same environment everywhere.”

---

## 2️⃣ Why Containers Are Used

### Key Benefits (MEMORIZE)

- 🚫 **No environment conflicts**
    
- ⚡ **Very fast startup (seconds)**
    
- 🪶 **Lightweight** (uses host OS)
    
- ☁️ **Perfect for Cloud & DevOps**
    
- 📈 **Easy to scale**
    

---

### Containers vs Virtual Machines (VERY IMPORTANT)

|Feature|Containers|Virtual Machines|
|---|---|---|
|Size|MBs|GBs|
|Startup|Seconds|Minutes|
|OS|Uses host OS|Full guest OS|
|Overhead|Very low|Heavy|
|Performance|Fast|Slower|

### 🏠 Analogy

- **Virtual Machine** → Entire house (kitchen, bathroom, furniture)
    
- **Container** → One room inside a shared house
    

---

## 3️⃣ What is Docker?

**Docker** is the most popular tool used to **create, run, and manage containers**.

Docker makes containerization:

- Easy
    
- Standardized
    
- Developer-friendly
    

---

## 4️⃣ Core Docker Concepts (HIGH VALUE)

### 🧠 Docker Architecture (Understand this flow)

```
Dockerfile → Image → Container
                ↓
            Registry
```

---

### 🔹 Docker Engine

- The **core runtime**
    
- Builds images
    
- Runs containers
    

👉 Think: **Docker’s brain**

---

### 🔹 Docker CLI

- Command-line tool
    
- You type commands like:
    

```bash
docker run
docker build
docker pull
```

👉 Think: **Remote control**

---

### 🔹 Docker Image

- A **blueprint**
    
- Read-only
    
- Created from a Dockerfile
    

👉 Like a **class** in Java

---

### 🔹 Docker Container

- A **running instance of an image**
    

👉 Like an **object** created from a class

---

### 🔹 Docker Registry

- Storage for images
    
- Example:
    
    - Docker Hub
        
    - Google Container Registry (GCR)
        

👉 Like **GitHub for images**

---

## 5️⃣ Docker Workflow (VERY IMPORTANT)

### Step-by-step lifecycle

1️⃣ **Dockerfile**  
→ Write instructions

2️⃣ **Image**  
→ Build blueprint

3️⃣ **Container**  
→ Run the image

---

## 6️⃣ Important Docker Commands (EXAM + LAB)

### 🔍 Check Docker Version

```bash
docker --version
```

---

### 📥 Pull an Image

```bash
docker pull nginx
```

Downloads image from Docker Hub

---

### ▶️ Run a Container

```bash
docker run -d -p 8080:80 nginx
```

Explanation:

- `-d` → detached mode (runs in background)
    
- `-p 8080:80` → port mapping
    
    - Host: 8080
        
    - Container: 80
        

---

### 📋 List Running Containers

```bash
docker ps
```

---

### ⏹ Stop a Container

```bash
docker stop <container_name>
```

---

### 🗑 Remove a Container

```bash
docker rm <container_name>
```

---

## 7️⃣ Practical Lab — Explained Clearly

---

## 🔹 Part 1: Running NGINX Container

### Step 1: Pull Image

```bash
docker pull nginx
```

---

### Step 2: Run Container

```bash
docker run -d -p 8080:80 --name my_web_server nginx
```

Now:

- NGINX runs inside container
    
- Browser accesses it via `localhost:8080`
    

---

### Step 3: Verify

🌐 Open browser:

```
http://localhost:8080
```

You should see:

> **Welcome to nginx!**

---

### Step 4: Manage Container

```bash
docker ps
docker stop my_web_server
docker rm my_web_server
```

---

## 🔹 Part 2: Build Your Own Docker Image

### Why do this?

To run **your own application**, not someone else’s image.

---

### Step 1: Create Project Folder

```bash
mkdir my-custom-app
cd my-custom-app
```

---

### Step 2: Create `index.html`

This is your app content.

---

### Step 3: Write Dockerfile (MOST IMPORTANT)

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```

🧠 Explanation:

- `FROM` → base image
    
- `COPY` → copy your file into container
    

---

### Step 4: Build Image

```bash
docker build -t custom-web:v1 .
```

- `-t` → tag name
    
- `.` → current directory
    

---

### Step 5: Run Custom Image

```bash
docker run -d -p 8081:80 custom-web:v1
```

Visit:

```
http://localhost:8081
```

🎉 **Your own Docker image is running**

---

## 8️⃣ Data Persistence with Volumes (CRITICAL CONCEPT)

### ❌ Problem

Containers are **ephemeral**

- Stop container → data gone
    
- Delete container → data gone
    

Bad for:

- Databases
    
- User uploads
    

---

### ✅ Solution: Docker Volumes

Volumes store data **outside the container lifecycle**.

---

### Volume Syntax

```bash
-v <volume_name>:<container_path>
```

---

### MySQL Example

```bash
docker run -d \
 -p 3306:3306 \
 --name mysql-db \
 -e MYSQL_ROOT_PASSWORD=secret \
 -v mysql_data:/var/lib/mysql \
 mysql:latest
```

📌 Meaning:

- `mysql_data` → volume on host
    
- `/var/lib/mysql` → MySQL data directory inside container
    

---

### Inspect Volumes

```bash
docker volume ls
```

---

### Clean Up

```bash
docker stop mysql-db
docker rm mysql-db
docker volume rm mysql_data
```

---

## 9️⃣ Docker Compose (Optional – Concept Only)

Docker Compose:

- Runs **multiple containers**
    
- Uses **YAML file**
    
- Ideal for:
    
    - Web + DB
        
    - Microservices
        

---

## 🔟 Session Outcomes (You Achieved)

✅ Why containers are used  
✅ Docker fundamentals  
✅ Run images  
✅ Build custom images  
✅ Persist data using volumes

---

## 🧠 One-Line Summary (EXAM GOLD)

> **Docker packages applications with all dependencies into lightweight containers that run consistently across environments.**

---

If you want, next we can:

- 🔥 Convert this into **exam notes**
    
- 🧪 Do **MCQs**
    
- 🧱 Learn **Docker Compose with example**
    
- 🚀 Learn **Docker for Java / Spring Boot**
    

Just tell me how you want to continue 😄