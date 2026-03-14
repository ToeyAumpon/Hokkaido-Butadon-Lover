# 🐷 北海道 豚丼 巡り — Hokkaido Butadon Bucket List

![CI](https://github.com/ToeyAumpon/Hokkaido-Butadon-Lover/actions/workflows/deploy.yml/badge.svg)

> "For everyone who loves Hokkaido Butadon as much as I do 🐷"

I am a 1st year IT vocational school student — this is my first portfolio project built with AWS!  
A web app to track and rate the best 豚丼 restaurants in Hokkaido, Japan.  
Built to demonstrate a full CI/CD pipeline on AWS.

🇯🇵 [日本語版はこちら](./README_JP.md)

---

## 📸 Live Demo

> Server terminated after demo.

![App Screenshot](screenshot/img2.png)
![App Screenshot](screenshot/img1.png)

---

## 💡 Why I Built This

- I love 豚丼 and I am from Hokkaido 🐷
- I want to work in infrastructure / cloud engineering after graduation
- I wanted to learn real DevOps skills: Docker, CI/CD, Linux server, AWS

> The app is the excuse. The pipeline is the point.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🗺 Restaurant List | 8 real restaurants in Obihiro and Sapporo |
| ✅ Visited Checkbox | Mark restaurants as visited — card turns green |
| ⭐ Star Rating | Rate each restaurant 1–5 stars |
| 🔍 Filter Tabs | Filter by city or visited / unvisited |
| 📊 Progress Bar | Track how many restaurants you have visited |

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, JavaScript |
| Backend | Node.js + Express.js |
| Containerization | Docker |
| Version Control | Git + GitHub |
| CI/CD Pipeline | GitHub Actions |
| Cloud Hosting | AWS EC2 |

---

## 🏗 Architecture

```
Browser
   ↓
AWS EC2 (Ubuntu Server)
   ↓
Docker Container
   ↓
Node.js + Express
   ↓
index.html (Frontend)

GitHub Actions (triggers on every git push to main)
   → Build Docker image → Deploy to EC2
```

---

## ⚙️ How It Works

### For Users
```
1. Open the app in a browser
2. Browse 8 real 豚丼 restaurants
3. Click a card to see address and notes
4. Rate it 1–5 stars ⭐
5. Click "Mark as Visited" ✅
6. Progress bar updates
```

### For Developers (CI/CD Pipeline)
```
git push → GitHub Actions triggers automatically
        → Build Docker image
        → Deploy to AWS EC2
        → App is live 🌐
```

---

## 📁 Project Structure

```
Hokkaido-Butadon-Lover/
├── public/
│   └── index.html        ← Frontend (HTML/CSS/JS)
├── server.js             ← Node.js + Express server
├── Dockerfile            ← Container definition
├── .dockerignore
├── .github/
│   └── workflows/
│       └── deploy.yml    ← GitHub Actions pipeline
├── package.json
└── README.md
```

---

## 🚀 Getting Started

### Run Locally
```bash
git clone https://github.com/ToeyAumpon/Hokkaido-Butadon-Lover.git
cd Hokkaido-Butadon-Lover
npm install
node server.js
# Open http://localhost:3000
```

### Run with Docker
```bash
docker build -t butadon-app .
docker run -p 3000:3000 butadon-app
# Open http://localhost:3000
```

---

## 🔧 Problems I Faced & How I Fixed Them

### 1. `docker build` failed — COPY error
- **Cause:** Missing `/` in `COPY package*.json .`
- **Fix:** Changed to `COPY package*.json ./`

---

### 2. Could not SSH into EC2
- **Cause:** Public IP address changed after stopping the instance
- **Fix:** Updated Security Group inbound rule with the new IP address

---

### 3. Port 3000 not reachable from browser
- **Cause:** Security Group had no inbound rule for port 3000
- **Fix:** Added Custom TCP port 3000 inbound rule

---

### 4. `node_modules` was pushed to GitHub
- **Cause:** Forgot to add `node_modules` to `.gitignore`
- **Fix:** Added `node_modules` to `.gitignore`

---

## 📚 What I Learned

| Skill | What I understood |
|---|---|
| Docker | Containers solve the "works on my machine" problem by bundling the app and its environment together |
| Dockerfile | Order matters — copy `package.json` first to use layer caching |
| GitHub Actions | CI/CD automates build and deploy on every push |
| AWS EC2 | A cloud server you can rent, control via SSH, and terminate when done |
| Security Groups | Act as a firewall — only open ports you actually need |
| Linux / Bash | `sudo`, `chmod`, `systemctl`, `docker ps` — real server commands |
| Git | `pull` before `push`. Commit messages tell the story of your project |

---

## 🔮 Future Features

- [ ] Google Maps embed — show restaurant locations on a map
- [ ] Comment field — write personal notes per restaurant
- [ ] Photo upload — attach a meal photo to each visit
- [ ] Database — persist data with MySQL on AWS RDS
- [ ] User login — each user has their own bucket list

---

## 🐷 About

