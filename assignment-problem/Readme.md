Dockerizing Node and Python Apps
--------------------------------

This repository contains two small apps:
- Node app (node-app)
- Python BMI app (python-app)

The instructions.txt in the repository require dockerizing both apps as two separate images, running containers for each, re-creating containers, cleaning up, rebuilding with named tags, and running new containers that auto-remove when stopped.

What changed (summary)
- Node image base updated to a specific version (node:18-alpine).
- Node image exposes port 3000 (as the app serves at root).
- Python image base updated to a specific version (python:3.11-slim).
- Both Dockerfiles now have clearer, more canonical build steps.
- No functional changes to the apps themselves.

Prerequisites
- Docker installed and running on your host.
- Access to this repository.
- Optional: curl or a browser to test HTTP access to the Node app.

Directory layout
- assignment-problem/
  - node-app/
  - python-app/

What you will do
1) Build two images (one for each app).
2) Launch a container for each image and verify they work.
3) Re-create containers with specific names and learn how to stop/restart.
4) Clean up all stopped/running containers and all created images.
5) Re-build images with explicit names/tags.
6) Run new containers based on re-built images with automatic removal when stopped.

Step-by-step guide
Note: Commands are shown with typical cross-platform syntax. Adjust as needed for your shell (bash, PowerShell, CMD).

1) Build the images (two separate images)
- Build Node app image:
  docker build -t assignment-node-app:1.0 -f node-app/Dockerfile .
- Build Python BMI app image:
  docker build -t assignment-python-app:1.0 -f python-app/Dockerfile .

2) Run containers (one per app)
- Run Node container (exposes port 3000):
  docker run -d --name node-app-container -p 3000:3000 assignment-node-app:1.0
  Test: curl http://localhost:3000/ or open http://localhost:3000/ in a browser
- Run Python BMI container (interactive):
  docker run -it --name python-app-container assignment-python-app:1.0
  Note: The BMI script is interactive (reads input from the terminal).

3) Re-create containers and assign names
- Stop and remove existing containers:
  docker stop node-app-container
  docker rm node-app-container
  docker stop python-app-container
  docker rm python-app-container
- Re-create containers with the same names:
  docker run -d --name node-app-container -p 3000:3000 assignment-node-app:1.0
  docker run -it --name python-app-container assignment-python-app:1.0

4) Clean up (remove) all stopped containers and all created images
- Remove stopped containers:
  docker container prune -f
- Remove unused images (optional, all images):
  docker image prune -a -f
- Or remove specific images:
  docker rmi assignment-node-app:1.0
  docker rmi assignment-python-app:1.0

5) Re-build with names/tags (recommended for versioning)
- Node image (new tag):
  docker build -t assignment-node-app:1.1 -f node-app/Dockerfile .
- Python image (new tag):
  docker build -t assignment-python-app:1.1 -f python-app/Dockerfile .

6) Run new containers from rebuilt images with auto-remove
- Node container (auto-remove on stop):
  docker run --rm --name node-app-container -p 3000:3000 assignment-node-app:1.1
- Python BMI container (auto-remove on stop, interactive):
  docker run --rm -it --name python-app-container assignment-python-app:1.1

Notes
- If you need to test the Node app behind a proxy or different port, adjust the -p flag accordingly.
- The Python BMI app is interactive; running with -it ensures you can provide input and see the result.
- The updated Dockerfiles reflect explicit base images and a clearer build flow, which helps with caching and reproducibility.
