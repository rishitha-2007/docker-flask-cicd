# Docker + Flask CI/CD Pipeline

A small Flask API that is automatically tested and containerised using **GitHub Actions** and **Docker**.

## What the pipeline does
On every push or pull request to `main`:
1. **test** job: installs dependencies and runs `pytest`.
2. **docker-build** job (runs only if tests pass): builds the Docker image, starts the container and checks that `/health` responds.

## Tech stack
Python, Flask, pytest, Docker, GitHub Actions

## Run locally
```bash
docker build -t flask-cicd-demo:latest .
docker run -p 5000:5000 flask-cicd-demo:latest
```
Open http://localhost:5000 and http://localhost:5000/health

## Run the tests
```bash
pip install -r requirements.txt
pytest -v
```

## Project structure
```
app.py                       Flask application
test_app.py                  Unit tests
Dockerfile                   Container image definition
.github/workflows/ci-cd.yml  CI/CD pipeline
```
