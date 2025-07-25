# Realtime Chat App - DevOps Deployment

A full-stack, real-time chat application deployed with Docker and prepared for Kubernetes orchestration. The app uses **React + TailwindCSS + Zustand** on the frontend, and **Node.js + Express + MongoDB + Socket.io** on the backend.

---

## 📦 Tech Stack

### 🚀 Frontend
- **React.js**
- **TailwindCSS**
- **Zustand** (for state management)
- **DaisyUI** (for UI components)
- Exposed on: `http://localhost:80`

### 🛠 Backend
- **Node.js**
- **Express**
- **MongoDB** (running on port `27017`)
- **Socket.io** (real-time communication)
- JWT-based authentication
- API exposed on: `http://localhost:5001`

### 🔧 DevOps & Infrastructure
- **Docker** (containerization)
- **Kubernetes** (planned orchestration)
- **NGINX** (as reverse proxy/web server)
- **GitHub** (version control)
- **Port Configuration:**
  - Frontend: `80`
  - Backend: `5001`
  - Database: `27017`

---

## 📁 Project Structure
chat-app/
├── client/ # React frontend
│ └── Dockerfile # Dockerfile for frontend
├── server/ # Express backend
│ └── Dockerfile # Dockerfile for backend (see below)
├── nginx/ # NGINX configuration (optional)
├── docker-compose.yml # (if used locally)
└── README.md

⚙️ How to Run (Local Docker Setup)
Clone the Repository

bash
Copy
Edit
git clone https://github.com/AkshatOPS/realtime-chatapp-devops.git
cd realtime-chatapp-devops
Start MongoDB (optional for local)

bash
Copy
Edit
docker run -d -p 27017:27017 --name mongo mongo
Build and Run Backend

bash
Copy
Edit
cd server
docker build -t chat-backend .
docker run -d -p 5001:5001 --env-file .env chat-backend
Build and Run Frontend

bash
Copy
Edit
cd ../client
docker build -t chat-frontend .
docker run -d -p 80:80 chat-frontend

🌍 Planned Improvements
 Setup Kubernetes manifests (Deployments, Services, Secrets)

 Add NGINX Ingress Controller

 Enable HTTPS with Let’s Encrypt

 Implement CI/CD pipeline with GitHub Actions

 Add logging/monitoring (Prometheus + Grafana)

 Unit tests and load testing

🧠 Notes
No Ingress Controller used yet — services are accessed via direct ports.

The backend health check is defined in the Dockerfile.

MongoDB is assumed to be running separately on port 27017.

Zustand is used for clean state management across components.

Styling is powered by TailwindCSS and DaisyUI for a modern look.

🙏 Acknowledgement
Special thanks to @iemafzalhassan for the original full-stack chat application repo.
This project is a DevOps-focused fork of their excellent work.

🤝 Contributions
Contributions are welcome. Feel free to fork the repo, open issues, or create pull requests.
>>>>>>> afb3f478b202e4368b8d4c32de63169775a2a534
