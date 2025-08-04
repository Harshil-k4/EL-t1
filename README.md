# Elevate Labs Task 1 – DevOps CI/CD Automation

This repository (`EL-t1`) contains the implementation of the DevOps Internship Task 1 for Elevate Labs. It demonstrates automated CI/CD deployment of a Node.js application using Docker and GitHub Actions.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Folder Structure](#folder-structure)
- [Step-by-Step Implementation Process](#step-by-step-implementation-process)
- [Running the Application](#running-the-application)
- [Best Practices Followed](#best-practices-followed)
- [Repository Link](#repository-link)

---

## Project Overview

A simple Node.js Express web application containerized with Docker and integrated with a CI/CD pipeline through GitHub Actions. Upon every push to the `main` branch, the pipeline runs automated tests, builds the Docker image using a multi-stage build for efficiency, and pushes the image to DockerHub.

---

## Folder Structure

EL-t1/
├── .github/
│ └── workflows/
│ └── main.yml
├── src/
│ └── index.js
├── package.json
├── Dockerfile
├── .dockerignore
├── README.md


---

## Step-by-Step Implementation Process

1. **Initialize the project and repository**
   - Created a new GitHub repository named `EL-t1`.
   - Structured the project according to best practices with clear separation of source code, Docker configuration, and CI/CD workflows.

2. **Develop Node.js application**
   - Built a minimal Express-based web server to serve as the application for CI/CD automation.

3. **Create Dockerfile with multi-stage build**
   - Developed a multi-stage Dockerfile to reduce the final image size by separating build dependencies from runtime environment.
   - Used a lightweight base image (`node:18-alpine`) to optimize image footprint and security.

4. **Add `.dockerignore` file**
   - Ensured unnecessary files and folders like `node_modules` and `.git` are excluded from the Docker build context, improving build efficiency.

5. **Configure GitHub Actions CI/CD workflow**
   - Defined automation workflow to be triggered on pushes to the `main` branch.
   - Workflow steps include code checkout, Node.js setup, dependency installation, test execution, Docker image build, login to DockerHub, and image push.

6. **Securely manage secrets**
   - Configured GitHub repository secrets for DockerHub credentials (`DOCKERHUB_USERNAME` and `DOCKERHUB_TOKEN`) to keep sensitive information confidential.

7. **Test CI/CD pipeline**
   - Verified the automated workflow by monitoring GitHub Actions runs and confirming successful image deployment to DockerHub.

---

## Running the Application

### Locally via Node.js
1. Clone the repository:
git clone https://github.com/Harshil-k4/EL-t1.git
cd EL-t1

2. Install dependencies:
npm ci

3. Start the application:
npm start

4. Access the application at [http://localhost:3000/](http://localhost:3000/)

### Using Docker
1. Build the Docker image:
docker build -t el-t1-node-app .

2. Run the Docker container:
docker run -p 3000:3000 el-t1-node-app

3. Access the application at [http://localhost:3000/](http://localhost:3000/)

---

## Best Practices Followed

- **Multi-stage Docker build:** Improves image size and security by separating build-time and runtime stages.
- **Minimal base image:** Used `node:18-alpine` for a smaller attack surface and optimized performance.
- **.dockerignore file:** Excludes unnecessary files from the build context to speed up builds.
- **Automated CI/CD pipeline:** Enables continuous integration and continuous deployment triggered on every push to the main branch.
- **Secure storage of secrets:** Utilized GitHub Actions secrets for DockerHub authentication avoiding hardcoded credentials.
- **Testing before deployment:** Ensured basic test step inclusion for pipeline robustness.
- **Health checks in Dockerfile:** Added to monitor container health and improve reliability.
- **Clear and consistent project structure:** Facilitates maintainability and scalability.

---

## Repository Link

The complete code and workflow definitions can be accessed at:  
[https://github.com/Harshil-k4/EL-t1](https://github.com/Harshil-k4/EL-t1)

---

This implementation showcases an end-to-end CI/CD pipeline setup suitable for real-world DevOps workflows, emphasizing automation, security, and efficiency.