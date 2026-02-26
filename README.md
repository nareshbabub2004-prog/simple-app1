# Simple App

A modern containerized Node.js application with Docker and Kubernetes support.

## 🚀 Quick Start

### Prerequisites
- Node.js 16+ (for local development)
- Docker & Docker Compose
- kubectl (for Kubernetes deployment)

### Local Development

```bash
# Install dependencies
npm install

# Run development server
npm run dev
```

The app will be available at `http://localhost:3000`

### Docker

```bash
# Build Docker image
docker build -t simple-app:latest ./app

# Run with Docker
docker run -p 3000:3000 simple-app:latest
```

### Docker Compose

```bash
# Start with Docker Compose
docker-compose up

# Stop
docker-compose down
```

## 📦 Project Structure

```
simple-app1/
├── .github/
│   └── workflows/
│       ├── ci.yml              # CI pipeline
│       └── deploy.yml          # Deployment pipeline
├── k8s/
│   └── app.yaml               # Kubernetes deployment
├── app/
│   ├── Dockerfile             # Docker image definition
│   ├── index.html             # Frontend
│   └── app.js                 # Express.js server
├── package.json               # Dependencies
└── README.md                  # Documentation
```

## 🔧 API Endpoints

- `GET /` - Main application page
- `GET /api/health` - Health check endpoint
- `GET /api/info` - Application information

## ☸️ Kubernetes Deployment

```bash
# Apply Kubernetes manifest
kubectl apply -f k8s/app.yaml

# Check deployment status
kubectl get deployments
kubectl get pods
kubectl get svc

# Port forward to access
kubectl port-forward svc/simple-app-service 3000:80
```

## 🔄 CI/CD Pipeline

The repository includes GitHub Actions workflows:

- **CI Pipeline** (`.github/workflows/ci.yml`): Runs on every push and pull request
  - Installs dependencies
  - Runs tests
  - Builds Docker image

- **Deploy Pipeline** (`.github/workflows/deploy.yml`): Runs on main branch push
  - Builds Docker image with commit SHA
  - Deploys to Kubernetes

## 📊 Environment Variables

- `NODE_ENV` - Set to 'production' in Kubernetes (default: 'development')
- `PORT` - Application port (default: 3000)

## 📝 License

MIT

## 👤 Author

nareshbabub2004-prog

---

**Happy Coding!** 🎉
