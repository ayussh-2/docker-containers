# To start the PostgreSQL container:

docker-compose up -d

# To stop the container:

docker-compose down

# To connect to the running PostgreSQL instance:

docker exec -it psql_db psql -U postgres

# Data is persisted in the 'pgdata' Docker volume.
