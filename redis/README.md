# Redis Docker Setup

This directory contains a complete Redis Docker setup with Redis Commander for easy management.

## Components

-   **Redis Server**: Latest Redis 7 Alpine image
-   **Redis Commander**: Web-based Redis management interface
-   **Persistent Storage**: Data persistence using Docker volumes
-   **Custom Configuration**: Redis configuration file for optimization

## Quick Start

1. Start the Redis stack:

    ```bash
    docker-compose up -d
    ```

2. Access Redis Commander (web interface):

    - URL: http://localhost:8081
    - This provides a graphical interface to manage your Redis instance

3. Connect to Redis via CLI:
    ```bash
    docker exec -it redis-server redis-cli
    ```

## Services

### Redis Server

-   **Port**: 6379
-   **Image**: redis:7-alpine
-   **Container Name**: redis-server
-   **Data Volume**: redis_data (persistent storage)

### Redis Commander

-   **Port**: 8081
-   **Image**: rediscommander/redis-commander:latest
-   **Container Name**: redis-commander

## Configuration

The `redis.conf` file contains optimized settings:

-   Memory limit: 256MB with LRU eviction
-   Persistence: Both RDB snapshots and AOF
-   Logging: Notice level
-   Security: Protected mode disabled (safe for development)

## Common Commands

### Start services

```bash
docker-compose up -d
```

### Stop services

```bash
docker-compose down
```

### View logs

```bash
docker-compose logs redis
docker-compose logs redis-commander
```

### Redis CLI access

```bash
docker exec -it redis-server redis-cli
```

### Check Redis info

```bash
docker exec -it redis-server redis-cli info
```

## Security Notes

-   The default configuration is optimized for development
-   For production use, uncomment and set the `requirepass` option in `redis.conf`
-   Consider enabling protected mode for production environments

## Data Persistence

Data is persisted using Docker volumes:

-   Volume name: `redis_data`
-   Mount point: `/data` in the container
-   Both RDB snapshots and AOF are enabled for maximum durability
