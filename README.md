# 🎙️ Online Podcast Manager
### IFN636 - Software Life Cycle Management | Assessment 1.2
**Student:** Lejan Daniel I. Perdio
**Student ID:** 12691429

---

## 📌 Project Overview

An Online Podcast Manager built with the MERN stack (MongoDB, Express, React, Node.js).
The system supports core functionalities such as creating, viewing, updating, and deleting
podcast episodes through an administrative interface, while allowing users to browse,
search, and play podcast content.

---

## 🚀 Features

- ✅ User Authentication (Register, Login, Logout)
- ✅ Role-based access control (Admin and User)
- ✅ Create, Read, Update, Delete podcast episodes
- ✅ Category management
- ✅ Audio playback
- ✅ Search and filter episodes
- ✅ Admin Dashboard (desktop design)
- ✅ CI/CD pipeline with GitHub Actions
- ✅ Self-hosted runner on AWS EC2
- ✅ Deployed on AWS EC2

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js |
| Backend | Node.js, Express.js |
| Database | MongoDB Atlas |
| Auth | JWT (JSON Web Tokens) |
| Deployment | AWS EC2 (t3.micro) |
| CI/CD | GitHub Actions + Self-hosted Runner |
| Process Manager | PM2 |
| Web Server | Nginx |

---

## ⚙️ Project Setup Instructions

### Prerequisites
- Node.js v18+
- MongoDB Atlas account
- Git
- Yarn

### 1. Clone the repository
```bash
git clone https://github.com/liperdio/sampleapp_IFQ636.git
cd sampleapp_IFQ636
```

### 2. Setup Backend
```bash
cd backend
npm install
```

Create a `.env` file inside `backend/`:
```
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
PORT=5001
```

Start the backend:
```bash
npm start
```

### 3. Setup Frontend
```bash
cd frontend
npm install
npm start
```

### 4. Open the app
```
http://localhost:3000
```

### 5. Create Admin Account
```bash
cd backend
node seeder.js
```

---

## 🌐 Public URL
```
http://13.236.117.200
```

---

## 🔑 Test Credentials

| Role | Email | Password |
|---|---|---|
| Admin | admin@podkas.com | Admin1234! |
| User | register a new account | your password |

---

## 🔗 GitHub Repository
```
https://github.com/liperdio/sampleapp_IFQ636
```

---

## 📦 Branch Structure

| Branch | Purpose |
|---|---|
| `main` | Production ready code |
| `feature/podcast-model` | MongoDB models (Podcast, Category) |
| `feature/category-model` | Category model |
| `feature/podcast-backend-api` | Backend API routes (CRUD) |
| `feature/podcast-frontend-crud` | Frontend pages and components |
| `feature/audio-playback` | Audio player feature |
| `feature/cicd-pipeline` | CI/CD pipeline setup |

---

## 🔄 CI/CD Pipeline

- **CI** — Runs on every push to main: installs dependencies and builds frontend
- **CD** — Runs on merge to main: deploys automatically to AWS EC2 via self-hosted runner

### Pipeline Steps:
1. Code pushed to GitHub
2. GitHub Actions triggers CI job
3. CI installs dependencies and builds frontend
4. CD job runs on self-hosted EC2 runner
5. App is automatically deployed and restarted

---

## 🖥️ EC2 Deployment Setup
```bash
# Install Node.js
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs

# Install PM2
sudo npm install -g pm2

# Install Nginx
sudo apt install nginx -y

# Clone repository
git clone https://github.com/liperdio/sampleapp_IFQ636.git

# Start backend
cd backend
pm2 start server.js --name backend
pm2 save

# Build frontend
cd ../frontend
yarn install
CI=false yarn run build
pm2 serve build/ 3000 --name "Frontend" --spa
pm2 save
```

---

## 📚 References

- Bonini, T. (2015). The second age of podcasting. *Quaderns del CAC*, 18(41), 21–30.
- Sullivan, J. L. (2019). The platforms of podcasting. *Social Media + Society*, 5(4).
- Sommerville, I. (2016). *Software engineering* (10th ed.). Pearson.