# database_servers
## Docker Compose Setup

To set up the database servers using Docker Compose, follow these steps:

1. **Install Docker and Docker Compose**: Ensure you have Docker and Docker Compose installed on your machine. You can download them from [Docker's official website](https://www.docker.com/).

2. **Clone the Repository**: Clone this repository to your local machine using:
    ```sh
    git clone https://github.com/suonsamoun/database_servers.git
    cd database_servers
    ```

3. **Create a `.env` File**: Create a `.env` file in the root directory of the project and add the necessary environment variables. For example:
    ```env
    POSTGRES_USER=postgres
    POSTGRES_PASSWORD=examplepassword
    POSTGRES_DB=exampledb

    MYSQL_ROOT_PASSWORD=examplerootpassword
    MYSQL_DATABASE=exampledb
    MYSQL_USER=exampleuser
    MYSQL_PASSWORD=examplepassword
    ```

4. **Run Docker Compose**: Use the following command to start the services defined in the `docker-compose.yml` file:
    ```sh
    docker-compose up -d
    ```

5. **Access the Services**: Once the services are up and running, you can access them using the appropriate ports defined in the `docker-compose.yml` file.

6. **Stop the Services**: To stop the services, run:
    ```sh
    docker-compose down
    ```

## Services

The following services are included in the `docker-compose.yml` file:

- **PostgreSQL**: A powerful, open-source object-relational database system.
- **Redis**: An in-memory data structure store, used as a database, cache, and message broker.
- **Redis Commander**: A web-based UI for managing and visualizing data in Redis.
- **Adminer**: A lightweight database management tool with support for multiple database systems, including PostgreSQL and MySQL.
- **phpMyAdmin**: A web-based interface for managing MySQL databases.

## Troubleshooting

If you encounter any issues, check the logs of the services using:
```sh
docker-compose logs
```

For more detailed information, refer to the official documentation of Docker and Docker Compose.