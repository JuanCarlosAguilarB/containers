
# RabbitMQ Setup using Docker

This repository contains configurations and instructions for setting up RabbitMQ using Docker.

## Getting Started

To get RabbitMQ up and running locally, follow these steps:

### 1. Docker Compose Configuration

Modify the `docker-compose.yml` file to include RabbitMQ service. Here's a basic example:

```yaml
version: '3'
services:
  rabbitmq:
    image: rabbitmq:management
    ports:
      - "5672:5672"   # RabbitMQ messaging port
      - "15672:15672" # RabbitMQ management UI
    environment:
      - RABBITMQ_DEFAULT_USER=user
      - RABBITMQ_DEFAULT_PASS=password
    volumes:
      - ./rabbitmq/data:/var/lib/rabbitmq
```

Adjust the configuration based on your specific requirements. This example sets up RabbitMQ with a management UI, exposes ports `5672` (for messaging) and `15672` (for management UI), and sets default credentials.

### 3. Environment Variables

Modify the environment variables (`RABBITMQ_DEFAULT_USER`, `RABBITMQ_DEFAULT_PASS`) in the `docker-compose.yml` file as needed.

### 4. Start RabbitMQ

Run Docker Compose to start RabbitMQ:

```bash
docker-compose up -d rabbitmq
```

This command starts RabbitMQ in detached mode (`-d`).

### 5. Access RabbitMQ Management UI

Open your web browser and go to `http://localhost:15672` to access the RabbitMQ management UI. Log in using the credentials you set in the `docker-compose.yml` file.

### 6. Using RabbitMQ

You can now use RabbitMQ in your Docker environment. Configure your applications to connect to `localhost:5672` for messaging.

### 7. Additional Configurations

- **SSL/TLS**: If you need to secure communications, configure RabbitMQ to use SSL/TLS. Update your `docker-compose.yml` accordingly.
- **Clustering**: For high availability and scalability, configure RabbitMQ clustering.
- **Persistence**: RabbitMQ data is stored in `./rabbitmq/data` (or your specified volume). Ensure data persistence and backups as per your needs.

### 8. Clean Up

To stop and remove RabbitMQ container:

```bash
docker-compose down
```

This removes the RabbitMQ container and its associated volumes.


---
## Also, we can run rabbit fast with following command:

```bash
docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.13-management
```
