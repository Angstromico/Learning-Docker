# Docker Learning Repository 🐳

Welcome to my Docker learning journey! This repository contains practical examples and exercises from the course **"Learn Docker, Docker Compose, Multi-Container Projects, Deployment and all about Kubernetes from the ground up!"** and other Docker learning resources.

## 📚 Course Overview

This repository serves as a comprehensive collection of hands-on Docker projects and examples as I progress through learning containerization, orchestration, and deployment strategies.

### Learning Path
- **Basic Docker Concepts** - Images, containers, Dockerfiles
- **Docker Compose** - Multi-container applications
- **Advanced Docker** - Networks, volumes, optimization
- **Kubernetes** - Container orchestration at scale
- **Deployment Strategies** - Production-ready configurations

## 🗂️ Repository Structure

```
Docker Learn/
├── Node-app-on-Docker/              # Node.js web application containerized
│   ├── Dockerfile                   # Docker configuration for Node app
│   ├── package.json                 # Node.js dependencies
│   ├── server.js                    # Express.js web server
│   ├── public/                      # Static assets
│   └── README.md                    # Project-specific documentation
├── python-app-starting-setup/       # Python application containerized
│   └── python-app-starting-setup/   # Simple Python RNG app
│       ├── Dockerfile               # Docker configuration for Python app
│       └── rng.py                   # Random number generator script
└── README.md                        # This file - repository overview
```

## 🚀 Featured Projects

### 1. Node.js Web Application (`Node-app-on-Docker/`)
A simple Express.js application demonstrating basic Docker containerization concepts.

**Key Features:**
- Web interface for setting and displaying course goals
- Port mapping and container networking
- Multi-stage Dockerfile optimization
- Development workflow with Docker

**Quick Start:**
```bash
cd Node-app-on-Docker
docker build -t node-course-app .
docker run -p 3000:80 node-course-app
```

### 2. Python Application (`python-app-starting-setup/`)
A basic Python random number generator application containerized for learning purposes.

**Quick Start:**
```bash
cd python-app-starting-setup/python-app-starting-setup
docker build -t python-rng-app .
docker run python-rng-app
```

## 🛠️ Prerequisites

Before working with the projects in this repository, ensure you have:

- **Docker Desktop** installed and running
- **Git** for version control
- **Code editor** (VS Code recommended with Docker extensions)
- **Command line/terminal** access

## 📖 Learning Resources

### Primary Course
- **Course**: "Learn Docker, Docker Compose, Multi-Container Projects, Deployment and all about Kubernetes from the ground up!"
- **Focus**: Practical, hands-on approach to containerization

### Additional Resources
- Official Docker Documentation
- Kubernetes Documentation
- Container Best Practices Guide

## 🎯 Learning Objectives

By the end of this learning journey, I aim to master:

1. **Container Fundamentals**
   - Building and optimizing Docker images
   - Managing containers and their lifecycle
   - Understanding container networking

2. **Multi-Container Applications**
   - Docker Compose for local development
   - Service discovery and communication
   - Volume management and data persistence

3. **Production Deployment**
   - Container orchestration with Kubernetes
   - CI/CD pipeline integration
   - Monitoring and logging strategies

4. **Best Practices**
   - Security considerations
   - Performance optimization
   - Scalability patterns

## 🔧 Common Docker Commands

### Image Management
```bash
# Build an image
docker build -t image-name .

# List images
docker images

# Remove an image
docker rmi image-name
```

### Container Management
```bash
# Run a container
docker run -d -p host-port:container-port --name container-name image-name

# List running containers
docker ps

# View container logs
docker logs container-name

# Stop a container
docker stop container-name

# Remove a container
docker rm container-name
```

### Docker Compose
```bash
# Start services
docker-compose up

# Start services in detached mode
docker-compose up -d

# Stop services
docker-compose down

# View logs
docker-compose logs
```

## 📝 Progress Tracking

This repository will evolve as I progress through the course:

- ✅ **Basic Docker** - Simple applications (Node.js, Python)
- 🔄 **Docker Compose** - Multi-container setups
- ⏳ **Advanced Topics** - Networks, volumes, optimization
- ⏳ **Kubernetes** - Orchestration and scaling
- ⏳ **Production** - Real-world deployment scenarios

## 🤝 Contributing

This is a personal learning repository, but feel free to:

- Use these examples for your own learning
- Suggest improvements or best practices
- Report issues or errors in the implementations

## 📄 License

This repository contains educational examples and is intended for learning purposes. Please refer to individual project licenses for specific usage terms.

## 📞 Connect

Learning Docker is an ongoing journey. If you have questions, suggestions, or want to share your own Docker learning experiences, feel free to reach out!

---

**Happy Containerizing! 🐳**
