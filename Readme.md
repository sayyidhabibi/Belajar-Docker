# Express Hello World - Dockerized 🚀

A simple Express.js application running inside Docker.

---

## 📦 Tech Stack

- Node.js 18
- Express.js
- Docker

---

## 📁 Project Structure

```
express-hello/
│── index.js
│── package.json
│── package-lock.json
│── Dockerfile
│── README.md
```

---

## 🚀 Run Without Docker (Local Development)

### 1️⃣ Install Dependencies

```bash
npm install
```

### 2️⃣ Start the Application

```bash
npm start
```

### 3️⃣ Open in Browser

```
http://localhost:3000
```

---

## 🐳 Run With Docker

### 1️⃣ Build Docker Image

```bash
docker build -t express-hello .
```

### 2️⃣ Run the Container

```bash
docker run -p 3000:3000 express-hello
```

### 3️⃣ Open in Browser

```
http://localhost:3000
```

If successful, you should see:

```
Hello World from Docker 🚀
```

---

## 🛑 Stop the Container

If running in foreground mode:

```
CTRL + C
```

If running in detached mode:

```bash
docker ps
docker stop <container_id>
```

---

## 🔎 Useful Docker Commands

### List Images

```bash
docker images
```

### List Running Containers

```bash
docker ps
```

---

## 🧹 Remove Image

```bash
docker rmi express-hello
```

---

## 🧠 Dockerfile Explanation

```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

Explanation:

- `FROM node:18-alpine` → Uses Node.js 18 Alpine base image
- `WORKDIR /app` → Sets working directory inside container
- `COPY package*.json ./` → Copies dependency files first (better caching)
- `RUN npm install` → Installs dependencies
- `COPY . .` → Copies all source code
- `EXPOSE 3000` → Exposes port 3000
- `CMD` → Command to run the application

---

## 🔥 Optional: Run in Detached Mode

```bash
docker run -d -p 3000:3000 --name express-app express-hello
```

Check logs:

```bash
docker logs express-app
```

---

## 📌 Notes

- Make sure Docker is installed
- Use `docker system prune` to clean unused images and containers

---

Happy Coding 🚀