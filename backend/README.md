# Backend - FastAPI with PostgreSQL

This directory contains the backend of the application built with FastAPI and a PostgreSQL database.

## Prerequisites

- Python 3.8 or higher
- Poetry (for dependency management)
- PostgreSQL (ensure the database server is running)

### Installing Poetry

To install Poetry, follow these steps:

```sh
curl -sSL https://install.python-poetry.org | python3 -
```

Add Poetry to your PATH (if not automatically added):

## Setup Instructions

1. **Navigate to the backend directory**:
    ```sh
    cd backend
    ```

2. **Install dependencies using Poetry**:
    ```sh
    poetry install
    ```
# Backend - FastAPI with PostgreSQL

This directory contains the backend of the application built with FastAPI.

## Prerequisites

- Python 3.8 or higher
- Poetry (for dependency management)
- PostgreSQL (ensure the database server is running)

### Installing Poetry

To install Poetry, follow these steps:
```sh
curl -sSL https://install.python-poetry.org | python3 -

Navigate to the backend directory:
3. **Set up the database with the necessary tables**:
    ```sh
    poetry run bash ./prestart.sh
    ```

4. **Run the backend server**:
    ```sh
    poetry run uvicorn app.main:app --reload
    ```

5. **Update configuration**:
   Ensure you update the necessary configurations in the `.env` file, particularly the database configuration.
Navigate to the backend directory:

sh

cd backend

Install dependencies using Poetry:

sh

poetry install

Set up the database with the necessary tables:

sh

poetry run bash ./prestart.sh

Run the backend server:

sh

    poetry run uvicorn app.main:app --reload

    Access the API:
    Open your browser and go to http://localhost:8000/docs.

Using Docker

    Build the Docker image:

    sh

docker build -t backend-app .

Run the Docker container:

sh

    docker run -d -p 8000:8000 backend-app

    Access the API:
    Open your browser and go to http://localhost:8000/docs.

Environment Variables

Ensure to update the necessary configurations in the .env file, particularly the database configuration.
Database Configuration

Ensure your PostgreSQL database is set up and running. Update the .env file with your database credentials:

php

POSTGRES_USER=<your_db_user>
POSTGRES_PASSWORD=<your_db_password>
POSTGRES_DB=<your_db_name>
DATABASE_URL=postgresql://<your_db_user>:<your_db_password>@<your_db_host>:5432/<your_db_name>

shell


### README for Docker Deployment

```markdown
# Full Stack Application Deployment with Docker

This guide provides instructions to deploy the full stack application using Docker and Docker Compose.

## Prerequisites

- Docker
- Docker Compose

## Setup Instructions

### Clone the Repository

```sh
git clone <repository-url>
cd <repository-directory>

Configure Environment Variables

Ensure all necessary environment variables are set in the .env files located in the frontend and backend directories.
Docker Compose Setup

    Build and run the containers:

    sh

docker-compose up --build -d

Verify the services are running:

sh

    docker ps

    Access the Frontend:
    Open your browser and go to http://<your-domain-or-ip>.

    Access the API:
    Open your browser and go to http://<your-domain-or-ip>/api.

    Access Adminer:
    Open your browser and go to http://<your-domain-or-ip>:8080.

    Access Nginx Proxy Manager:
    Open your browser and go to http://<your-domain-or-ip>:81.

Domain and SSL Configuration

Configure your domain (or get a free subdomain from Afraid DNS). Set up DNS records to point to your EC2 instance's IP. Ensure HTTP redirects to HTTPS and www redirects to non-www.
Nginx Proxy Manager Configuration

    Access Nginx Proxy Manager:
    Open a web browser and navigate to http://<your-ec2-ip>:81.

    Add a New Proxy Host for the Frontend:
        Domain Names: my_appik.afraid.org
        Scheme: http
        Forward Hostname / IP: nodejs_app
        Forward Port: 5173
        Websockets Support: Enabled
        SSL: Enable SSL (Let's Encrypt)

    Add Another Proxy Host for the Backend:
        Domain Names: my_appik.afraid.org
        Scheme: http
        Forward Hostname / IP: fastapi_app
        Forward Port: 8000
        Custom Locations:
            Location: /api
            Scheme: http
            Forward Hostname / IP: fastapi_app
            Forward Port: 8000
            Websockets Support: Enabled
            Location: /docs
            Scheme: http
            Forward Hostname / IP: fastapi_app
            Forward Port: 8000
            Websockets Support: Enabled
            Location: /redoc
            Scheme: http
            Forward Hostname / IP: fastapi_app
            Forward Port: 8000
            Websockets Support: Enabled

Troubleshooting

If you encounter any issues, please check the logs of each container using the following command:

sh

docker logs <container_name>

For further assistance, refer to the official documentation of the respective services.

vbnet


These README templates provide detailed instructions on how to deploy the frontend and backend manually and using Docker. Be sure to customize the placeholders (like `<repository-url>`, `<repository-directory>`, `<your-domain-or-ip>`, etc.) with actual values specific to your setup.


