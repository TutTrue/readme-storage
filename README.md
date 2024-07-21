# SpaceJat

This repository contains the SpaceJat backend project that provides microservices structure communicating using Nats message broker powering the tow messaging models, publish/subscribe model, and message queue model with the use of WebSocket functionalities. Below are the instructions on how to run the server and access the client interfaces.


## Prerequisites

- [Docker](https://www.docker.com/get-started)
- [Node.js](https://nodejs.org/) and [npm](https://www.npmjs.com/) (if running without Docker)

## navigate to backend folder

```bash
cd backend
```

## Running with Docker

### Step 1: Build Docker Images

Navigate to the project directory and run:

```bash
sudo docker-compose build
```

### Step 2: Start Services

Run all services with:

```bash
sudo docker-compose up
```

## Running Without Docker

### Step 1: Run NATS Server

Ensure a NATS server is running locally:

```bash
nats-server -DV
```

### Step 2: Install Dependencies

Navigate to the project directory and run:

```bash
npm install
```

### Step 3: Start Services

Run each service in a separate terminal:

```bash
node services/cloud-services/drive-service.js
node services/cloud-services/S3-service.js
node services/meeting-service.js
node services/notification-service.js
node services/timeline-service.js
```


## WebSocket Server

### Connection

Connect to the WebSocket server at:

```
ws://localhost:8765
```

### Message Format

Send messages in JSON format:

```json
{
    "meeting-host": "Sarah",
    "recorded": true
}
```
