# Flask Todo App

A containerized Todo List application built with **Flask**, featuring Docker support, CI/CD automation, and cloud deployment using Terraform on AWS.

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Flask](https://img.shields.io/badge/Flask-3.0.3-black)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?logo=githubactions)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?logo=terraform)
![AWS](https://img.shields.io/badge/AWS-FF9900?logo=amazonaws)

---

## Features

* Add new tasks
* Mark tasks as completed
* Delete tasks
* Persistent JSON-based storage
* Docker containerization
* Automated CI/CD with GitHub Actions
* Infrastructure provisioning with Terraform
* Ready for deployment on AWS EC2

---

## Quick Start

### Run Locally

Install the required Python dependencies:

```bash
pip install -r requirements.txt
```

Start the Flask application:

```bash
python app.py
```

Open your browser and visit:

```text
http://127.0.0.1:5000
```

### Run with Docker

Build the Docker image:

```bash
docker build -t todo-app .
```

Run the container:

```bash
docker run -p 5000:5000 todo-app
```

Then open:

```text
http://localhost:5000
```

### Deploy to AWS

Initialize Terraform:

```bash
terraform init
```

Review and apply the infrastructure:

```bash
terraform apply
```

> **Note:** AWS credentials and the required Terraform configuration must be set up before deployment.

---

## Tech Stack

| Layer                  | Technology     |
| ---------------------- | -------------- |
| Frontend               | HTML, CSS      |
| Backend                | Python, Flask  |
| Containerization       | Docker         |
| CI/CD                  | GitHub Actions |
| Infrastructure as Code | Terraform      |
| Cloud                  | AWS EC2        |
| Data Storage           | JSON           |

---

## Project Structure

```text
.
├── .github/
│   └── workflows/
│       └── ci.yml
├── static/
│   └── style.css
├── templates/
│   └── index.html
├── app.py
├── todos.json
├── requirements.txt
├── Dockerfile
├── main.tf
└── README.md
```

---

## Application Architecture

```text
User
  │
  ▼
Flask Web Application
  │
  ├── HTML/CSS Frontend
  │
  └── JSON Storage
        │
        ▼
    todos.json

Docker
  │
  ▼
Containerized Flask Application

GitHub
  │
  ▼
GitHub Actions
  │
  ▼
CI/CD Pipeline

Terraform
  │
  ▼
AWS EC2
  │
  ▼
Dockerized Flask Application
```

---

## CI/CD

The project uses **GitHub Actions** to automate the CI/CD workflow.

The workflow is defined in:

```text
.github/workflows/ci.yml
```

The pipeline can be used to automatically test and validate changes whenever code is pushed to the repository.

---

## Infrastructure as Code

AWS infrastructure is defined using **Terraform**.

The main Terraform configuration is:

```text
main.tf
```

Terraform allows the AWS infrastructure to be provisioned and managed as code.

---

## Data Persistence

The application stores Todo data in:

```text
todos.json
```

The file provides simple JSON-based persistent storage for the application.

> **Important:** When running the application inside Docker, data stored inside the container can be lost when the container is removed unless `todos.json` is mounted using a Docker volume or bind mount.

---

## Docker

The application is containerized using the `Dockerfile`.

Build the image:

```bash
docker build -t todo-app .
```

Run the container:

```bash
docker run -p 5000:5000 todo-app
```

The application is exposed on port:

```text
5000
```

---

## Future Improvements

* Add a database such as PostgreSQL
* Add automated tests
* Add Docker Compose
* Add HTTPS with Nginx
* Add monitoring and logging
* Improve CI/CD with automated Docker image builds
* Add deployment automation to AWS EC2
* Add infrastructure variables and outputs to Terraform
