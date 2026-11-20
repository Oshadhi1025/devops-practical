
# DevOps Practical – Flask Application

## Project Overview

This project demonstrates a complete DevOps workflow using a simple Python Flask web application. It covers version control, automated testing, containerization, Kubernetes orchestration, self-healing, and continuous deployment.

## Technologies Used

- Python 3.9
- Flask 3.0.0
- Pytest 7.4.0
- Git and GitHub
- GitHub Actions
- Docker and Docker Hub
- Kubernetes, kubectl and Minikube
- Vercel (Cloud Deployment)

## Phase 1: Local Development and Version Control

Created a Flask application and an automated test using Pytest.

The project source code was committed and pushed to GitHub.

## Phase 2: Continuous Integration (CI)

Configured a GitHub Actions workflow in `.github/workflows/ci.yml`.

The workflow automatically installs dependencies and runs Pytest when changes are pushed to the `main` branch.

The latest CI pipeline completed successfully.

## Phase 3: Docker Containerization

Created a Dockerfile to package the Flask application with its dependencies.

Built and tested the Docker image locally and pushed version `v1` to Docker Hub.

Docker Hub Image:
https://hub.docker.com/r/oshadhi1025/flask-app

## Phase 4: Kubernetes Orchestration

Used Minikube to deploy the Docker container to a local Kubernetes cluster.

Configured a Kubernetes Deployment with two replicas and a NodePort Service to access the application.

Both Pods reached the Running state.

## Phase 5: Kubernetes Self-Healing Test

Deleted one running Pod using `kubectl delete pod`.

Kubernetes automatically created a replacement Pod to maintain the desired state of two replicas.

This demonstrated Kubernetes self-healing.

## Phase 6: Continuous Deployment (CD)

Deployed the Flask application publicly using Vercel, connected to the GitHub repository.

Updated the application message from V1 to V2 and pushed the changes to GitHub.

GitHub Actions successfully completed the automated tests, and Vercel automatically deployed the updated application.

**Note:** The practical instructions specified Render. However, Render required payment-card verification, so Vercel was used as an alternative hosting platform. The Vercel deployment uses its Flask/Python integration rather than the Docker-based Render deployment.

## Live Application

https://devops-practical-xi.vercel.app

### Final Output

Hello, DevOps World! V2 - Automatically Deployed on Vercel!

## Run the Application Locally

Install dependencies:

```bash
pip install -r requirements.txt
```

Start the Flask application:

```bash
python app.py
```

Open http://localhost:5000 in a browser.

## Run Automated Tests

```bash
python -m pytest
```

## Docker Commands

```bash
docker build -t flask-app:v1 .
docker run -p 5000:5000 flask-app:v1
```

## Kubernetes Commands

```bash
minikube start
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl get pods
minikube service flask-service
```

## GitHub Repository

https://github.com/Oshadhi1025/devops-practical

## Conclusion

This practical demonstrated key DevOps concepts, including version control, continuous integration, containerization, Kubernetes orchestration, self-healing, and automated cloud deployment.
