# MongoDB Docker Container

This repository contains a `docker-compose.yml` file to set up a MongoDB container with authentication.

## Prerequisites

-   Docker
-   Docker Compose

## Getting Started

1.  **Clone the repository:**

    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2.  **Create a `config.env` file:**

    Create a `config.env` file in the root of the project and add the following environment variables:

    ```
    MONGO_INITDB_ROOT_USERNAME=user
    MONGO_INITDB_ROOT_PASSWORD=password
    ```

3.  **Start the container:**

    ```bash
    docker-compose up -d
    ```

4.  **Connect to MongoDB:**

    You can connect to the MongoDB instance using the following connection string:

    ```
    mongodb://user:password@localhost:27017
    ```

## Stop the container

To stop the container, run the following command:

```bash
docker-compose down
```
