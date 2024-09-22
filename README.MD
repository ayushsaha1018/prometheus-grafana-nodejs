# Prometheus-Grafana-NodeJS

This project is a simple Node.js application designed to explore Prometheus and Grafana. It's built with TypeScript and uses the `prom-client` library to create and expose metrics.

## Overview

The application consists of three main components:

1. A Node.js application that generates metrics
2. Prometheus for scraping and storing the metrics
3. Grafana for visualizing the metrics

All components are containerized using Docker and run in a single network for easy inter-communication.

## Prerequisites

- Docker
- Docker Compose

## Project Structure

```
.
├── Dockerfile
├── docker-compose.yml
├── src/
│   └── (TypeScript source files)
├── package.json
└── README.md
```

## Getting Started

1. Clone this repository:
   ```
   git clone https://github.com/ayushsaha1018/prometheus-grafana-nodejs.git
   cd prometheus-grafana-nodejs
   ```

2. Start the application using Docker Compose:
   ```
   docker-compose up -d
   ```

3. Access the different components:
   - Node.js application: http://localhost:3000
   - Prometheus: http://localhost:9090
   - Grafana: http://localhost:3001

4. Log in to Grafana:
   - URL: http://localhost:3001
   - Initial credentials:
     - Username: admin
     - Password: admin
   - You will be prompted to change the password after the first login.

## Components

### Node.js Application

- Written in TypeScript
- Uses `prom-client` to create and expose metrics
- Exposes metrics on the `/metrics` endpoint

### Prometheus

- Scrapes metrics from the Node.js application
- Stores time-series data
- Accessible at http://localhost:9090

### Grafana

- Visualizes metrics collected by Prometheus
- Accessible at http://localhost:3001

## Configuration

The `docker-compose.yml` file sets up the entire environment, including:

- Building and running the Node.js application container
- Setting up Prometheus with the appropriate configuration
- Setting up Grafana with default settings

## Development

To modify the Node.js application:

1. Make changes to the TypeScript files in the `src/` directory
2. Rebuild the Docker image:
   ```
   docker-compose build
   ```
3. Restart the services:
   ```
   docker-compose up -d
   ```