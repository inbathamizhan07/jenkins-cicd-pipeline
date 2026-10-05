# Jenkins CI/CD Pipeline - Task 2

## Objective
Set up a basic Jenkins pipeline that automatically builds, tests and deploys a Node.js application using Docker.

## Tools Used
- Jenkins
- Docker and Docker Hub
- GitHub
- Node.js

## What I Did
1. Created a simple Node.js app (`server.js`) and a `Dockerfile` for it.
2. Ran Jenkins in a Docker container on my laptop.
3. Added my Docker Hub credentials to Jenkins securely.
4. Wrote a `Jenkinsfile` with the pipeline stages.
5. Created a Jenkins Pipeline job that reads the `Jenkinsfile` from this GitHub repo.
6. Tested the pipeline by pushing a change and checking the Jenkins dashboard.

## Pipeline Stages
| Stage | What it does |
|-------|--------------|
| Checkout | Pulls the latest code from GitHub |
| Build | Runs `npm install` and builds the Docker image |
| Test | Runs `npm test` |
| Push | Pushes the image to Docker Hub |
| Deploy | Runs the container on port 3000 |

## Automatic Trigger
Jenkins checks GitHub every 2 minutes (`pollSCM`). When I pushed a new commit, build #5 started by itself ("Started by an SCM change") and the app updated to the new version.

## Files in this Repo
- `Jenkinsfile` - the pipeline definition
- `Dockerfile` - builds the app image
- `Dockerfile.jenkins` - builds the Jenkins image with Docker and Node.js
- `server.js` and `package.json` - the Node.js app

## Screenshots

### Pipeline stages
![Stage View](screenshots/stage-view.png)

### Automatic trigger on commit
![SCM trigger](screenshots/scm-trigger.png)

### Build success
![Build success](screenshots/build-success.png)

### App running
![App running](screenshots/app-running.png)

## Outcome
I learned how to automate building, testing and deploying an application with a Jenkins pipeline.