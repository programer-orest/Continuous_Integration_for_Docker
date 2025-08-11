# GitHub Actions Workflow with Docker Build & Push to DockerHub

## Project Overview

This project extends the existing GitHub Actions CI workflow by automating the build and push of Docker images to DockerHub.  
It enables packaging the application into a Docker container and securely uploading it to a DockerHub repository for easier deployment and distribution.

## Tech Stack

- **GitHub Actions (CI/CD)**
- **Docker**
- **DockerHub Registry**
- **GitHub Repository Secrets** for secure credentials management

## What was done

- Added a new job called `docker-ci` to the GitHub Actions workflow.  
- Docker images are tagged with the current commit hash for traceability.  
- DockerHub credentials are securely stored and accessed via GitHub Repository Secrets.  
- The `docker-ci` job runs only on the `main` branch to ensure production readiness.  
- Uploading artifacts from previous jobs is restricted to runs on the `main` branch.  
- Steps in the `docker-ci` job include:  
  1. Logging into DockerHub Registry.  
  2. Building the Docker image using the provided `Dockerfile`.  
  3. Pushing the tagged Docker image to the DockerHub Registry.  

