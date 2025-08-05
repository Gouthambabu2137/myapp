# Jenkins CI/CD Pipeline – Task 2

## Objective

This project demonstrates a basic CI/CD pipeline using Jenkins and Docker to automate the build, test, and deployment of a Node.js application. It was created as part of a DevOps learning task focused on understanding continuous integration and continuous deployment workflows.

## Technologies Used

- Jenkins (Docker-based setup)
- Docker
- Git & GitHub
- Node.js (for sample application)

## Repository Structure

├── Dockerfile # Builds the Node.js application image
├── Jenkinsfile # Defines the Jenkins pipeline stages
├── package.json # Node.js app metadata and dependencies
├── app.js # Entry point of the sample Node.js app
└── README.md # Project documentation


## Jenkinsfile Overview

The `Jenkinsfile` defines the following stages:

### 1. **Build**
- Builds a Docker image from the `Dockerfile` using the application code.

### 2. **Test**
- Placeholder for running tests. For demonstration, it prints a success message.

### 3. **Deploy**
- Removes any previously running container (`myapp-container`) if it exists.
- Starts a new container from the freshly built image on port 3000.

## Jenkins Setup Details

- Jenkins runs in a Docker container.
- Docker socket is mounted inside the Jenkins container to allow Docker CLI commands.
- Pipeline is triggered on code push to the `main` branch of this repository.
- GitHub repository is configured as the SCM source.

## Trigger Configuration

The pipeline is automatically triggered via a webhook or polling mechanism upon each `git push` to the `main` branch.

## Outcome

The project successfully demonstrates a CI/CD pipeline that:
- Clones code from GitHub,
- Builds a Docker image,
- Optionally runs tests,
- Deploys the application using Docker.

## How to Reproduce

1. Clone this repository.
2. Ensure Docker and Jenkins are installed (Jenkins must have access to Docker).
3. Create a new Jenkins pipeline project and connect it to this repository.
4. Ensure Docker socket is mounted (`/var/run/docker.sock`) in Jenkins container.
5. Run the pipeline or push new changes to trigger it automatically.

## Author

**Goutham Babu** 
