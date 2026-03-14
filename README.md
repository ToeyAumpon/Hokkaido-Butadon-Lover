# 🐷 北海道 豚丼 巡り — Hokkaido Butadon Bucket List

"FOR WHO LOVE BUTADON LIKE ME"
A web application to track and rate the best 豚丼 (pork bowl) restaurants in Hokkaido, Japan.
Built as a portfolio project to demonstrate a full CI/CD deployment pipeline on AWS.

---

## 📖 Introduction

This app shows a curated list of 8 real 豚丼 restaurants across Obihiro (帯広) and Sapporo (札幌) — the two most famous cities for butadon in Hokkaido. Users can track which restaurants they have visited and give each one a personal star rating.

The frontend is intentionally simple. The real purpose of this project is the **deployment pipeline** around it — Docker, GitHub Actions, and AWS EC2.

---

## 💡 Why I Built This

- I love 豚丼 and I am from Hokkaido 🐷
- I want to work in infrastructure / cloud engineering after graduation
- This project covers real DevOps skills: Docker, CI/CD, Linux server, AWS

> The app is the excuse. The pipeline is the point.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🗺 Restaurant List | 8 real restaurants in Obihiro and Sapporo |
| ✅ Visited Checkbox | Mark restaurants as visited — card turns green |
| ⭐ Star Rating | Rate each restaurant 1–5 stars with a fun Japanese reaction |
| 🔍 Filter Tabs | Filter by city (帯広 / 札幌) or visited / unvisited |
| 📊 Progress Bar | Tracks how many restaurants you have visited out of 8 |

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Backend | Node.js + Express.js |
| Containerization | Docker |
| Version Control | Git + GitHub |
| CI/CD Pipeline | GitHub Actions |
| Cloud Hosting | AWS EC2 (t2.micro) |

---

## ⚙️ Workflows

### Non-Technical (User Story)

```
1. Open the app in a browser
2. See a list of 8 restaurants with city tags and Google ratings
3. Click a card to expand — see address and notes
4. Click stars to rate the restaurant
5. Click 「訪問済みにする」to mark it as visited
6. Card turns green, progress bar increases
7. Use filter tabs to view visited / unvisited restaurants
```

### Technical (DevOps Pipeline)

```
Developer writes code
      ↓
git commit + git push → GitHub (main branch)
      ↓
GitHub Actions triggers automatically
      ↓
Build Docker image → Run tests
      ↓
Deploy to AWS EC2 via SSH
      ↓
App is live at public EC2 URL 🌐
```

---

## 📁 Project Structure

```
hokkaido-butadon-map/
├── public/
│   └── index.html          ← Frontend app (HTML/CSS/JS)
├── server.js               ← Node.js + Express server
├── Dockerfile              ← Container definition
├── .github/
│   └── workflows/
│       └── deploy.yml      ← GitHub Actions CI/CD pipeline
├── package.json
└── README.md
```

---

## 🚀 Getting Started

### Run locally

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/hokkaido-butadon-map.git
cd hokkaido-butadon-map

# Install dependencies
npm install

# Start the server
node server.js

# Open in browser
http://localhost:3000
```

### Run with Docker

```bash
# Build the image
docker build -t butadon-app .

# Run the container
docker run -p 3000:3000 butadon-app

# Open in browser
http://localhost:3000
```

---

## 📦 Git Commit History (Step by Step)

| Step | Commit Message |
|---|---|
| 1 | `feat: add frontend HTML/CSS/JS app` |
| 2 | `feat: add Node.js Express server` |
| 3 | `feat: add Dockerfile` |
| 4 | `ci: add GitHub Actions deploy workflow` |
| 5 | `feat: deploy to AWS EC2` |
| 6 | `docs: update README with live URL` |

---

## 🔮 Future Features

- [ ] Google Maps embed — show restaurant locations on a map
- [ ] Comment/memo field — write personal notes per restaurant
- [ ] Photo upload — attach a meal photo to each visit
- [ ] Backend database — persist data with MySQL or PostgreSQL (AWS RDS)
- [ ] User login — multiple users with their own bucket list
- [ ] Share feature — shareable link of your bucket list progress

---

## 📚 What I Learned

| Skill | Detail |
|---|---|
| HTML / CSS / JS | Built interactive UI without any framework |
| DOM manipulation | Used addEventListener and classList to update the page dynamically |
| Node.js | Served static files using Express.js |
| Docker | Wrote a Dockerfile and containerized the app |
| GitHub Actions | Wrote a CI/CD workflow YAML file |
| AWS EC2 | Launched a Linux server, connected via SSH, ran Docker container |
| Linux (Bash) | Used ssh, docker run, systemctl on a real server |

---

## 🐷 About

Made with love for Hokkaido 豚丼 by an IT student from Japan.

**Live URL:** http://YOUR-EC2-IP:3000

 now understand:
- Why Docker exists — environment isolation
- How a `Dockerfile` works — a recipe with cached layers
- Why `package*.json` is copied first — layer caching optimization
- What `.dockerignore` does — keeps the image clean and small
- What `-p` does — opens a door between host and container

![CI](https://github.com/ToeyAumpon/Hokkaido-Butadon-Lover/actions/workflows/deploy.yml/badge.svg)