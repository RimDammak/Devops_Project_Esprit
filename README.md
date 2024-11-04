
---

# DevOps Project: Spring Boot Application with MySQL

This project demonstrates a complete DevOps workflow using a Spring Boot application connected to a MySQL database, deployed via Docker and managed by Jenkins for Continuous Integration and Continuous Deployment (CI/CD).

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [CI/CD Pipeline](#cicd-pipeline)
- [License](#license)

## Prerequisites

Before you begin, ensure you have met the following requirements:

- [Docker](https://docs.docker.com/get-docker/) installed on your machine.
- [Docker Compose](https://docs.docker.com/compose/install/) installed.
- [Jenkins](https://www.jenkins.io/doc/book/installing/) set up and running.
- Access to a Git repository (e.g., GitHub).

## Getting Started

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/RimDammak/Devops_Project_Esprit.git
   cd Devops_Project_Esprit
   ```

2. **Build the Docker Image**:
   You can manually build the Docker image with:
   ```bash
   docker build -t dammakrim/springbootapplication:latest .
   ```

3. **Run the Application**:
   Use Docker Compose to start the application and MySQL database:
   ```bash
   docker-compose up -d --build
   ```

4. **Access the Application**:
   Your application will be accessible at `http://localhost:8087`.

## Project Structure

- `Dockerfile`: Instructions for building the Docker image for the Spring Boot application.
- `docker-compose.yml`: Defines the services, including the Spring Boot application and MySQL database.
- `Jenkinsfile`: Contains the pipeline definition for CI/CD automation.

## Usage

You can test the API endpoints using [Postman](https://www.postman.com/) or curl. Example endpoint:
```bash
curl -X POST http://localhost:8087/tpfoyer/chambre/add-chambre -H "Content-Type: application/json" -d '{"key":"value"}'
```

## CI/CD Pipeline

The Jenkins pipeline automates the following steps:

1. Clones the repository.
2. Builds the application using Maven.
3. Runs tests and performs static code analysis.
4. Builds and pushes the Docker image to Docker Hub.
5. Deploys the application using Docker Compose.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

