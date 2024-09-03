# MERN Stack Application Deployment using Docker and Docker Compose

This repository contains a three-tier MERN (MongoDB, Express, React, Node.js) stack application deployed using Docker and Docker Compose. The application is designed to run on an Ubuntu EC2 instance on AWS. The setup consists of the following:

1. **Frontend**: A React.js application running on port 5173.
2. **Backend**: A Node.js application using Express.js, running on port 5050.
3. **Database**: MongoDB running on the default port 27017.

## Overview

### Architecture

The application is structured as a three-tier architecture:

- **Frontend**: React.js application that serves the user interface.
- **Backend**: Node.js with Express.js for handling application logic and API requests.
- **Database**: MongoDB for data storage.

### Networking

All containers are connected using a custom Docker network to allow communication between them. This isolated network ensures that the frontend, backend, and database can interact seamlessly.

### Volumes

A Docker volume is used to persist MongoDB data, ensuring that the data remains even if the container is restarted or removed.

## Setup

### 1. Environment Setup

- An EC2 instance running Ubuntu was set up as the deployment environment.
- Docker and Docker Compose were installed on the EC2 instance.

### 2. Docker and Docker Compose Configuration

- Dockerfiles were created for both the frontend and backend services to define their respective environments and dependencies.
- A `docker-compose.yaml` file was written to manage the multi-container application setup, defining the frontend, backend, and MongoDB services.

### 3. Handling CORS Issues

To handle CORS issues due to the frontend and backend running on different ports, CORS was configured in the backend. This was done in the `server.js` file, using CORS middleware to allow requests from the frontend to the backend.

### 4. Docker Compose

The `docker-compose.yaml` file, included in this repository, defines the services, networking, and volume configurations necessary to run the application.

## Running the Application

To start the application, run the following command in the directory containing the `docker-compose.yaml` file:


```bash
docker-compose up -d


note: update the record and recordlist files in this files developers have menitoned the localhost please change it to your ip address
