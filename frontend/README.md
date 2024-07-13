# Frontend - ReactJS with ChakraUI

This directory contains the frontend of the application built with ReactJS and ChakraUI.

## Prerequisites

- Node.js (version 14.x or higher)
- npm (version 6.x or higher)

## Setup Instructions

1. **Navigate to the frontend directory**:
    ```sh
    cd frontend
    ```

2. **Install dependencies**:
    ```sh
    npm install
    ```

3. **Run the development server**:
    ```sh
    npm run dev
    ```
# Frontend - ReactJS with ChakraUI

This directory contains the frontend of the application built with ReactJS and ChakraUI.

## Prerequisites

- Node.js (version 14.x or higher)
- npm (version 6.x or higher)

## Setup Instructions

### Manually

1. **Navigate to the frontend directory**:
    ```sh
    cd frontend
    ```

2. **Install dependencies**:
    ```sh
    npm install
    ```

3. **Run the development server**:
    ```sh
    npm run dev
    ```

4. **Access the application**:
    Open your browser and go to `http://localhost:5173`.

### Using Docker

1. **Build the Docker image**:
    ```sh
    docker build -t frontend-app .
    ```

2. **Run the Docker container**:
    ```sh
    docker run -d -p 5173:5173 frontend-app
    ```

3. **Access the application**:
    Open your browser and go to `http://localhost:5173`.

## Environment Variables

Ensure to set up the necessary environment variables in the `.env` file before running the application.

4. **Configure API URL**:
   Ensure the API URL is correctly set in the `.env` file.

