# database_servers
## Docker Compose Setup

To set up the database servers using Docker Compose, follow these steps:

1. **Install Docker and Docker Compose**: Ensure you have Docker and Docker Compose installed on your machine. You can download them from [Docker's official website](https://www.docker.com/).

2. **Clone the Repository**: Clone this repository to your local machine using:
    ```sh
    git clone https://github.com/yourusername/database_servers.git
    cd database_servers
    ```

3. **Create a `.env` File**: Create a `.env` file in the root directory of the project and add the necessary environment variables. For example:
    ```env
    POSTGRES_USER=yourusername
    POSTGRES_PASSWORD=yourpassword
    POSTGRES_DB=yourdatabase
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
- **MySQL**: An open-source relational database management system.

## Example `docker-compose.yml`

Here is an example of what your `docker-compose.yml` file might look like:

```yaml
version: '3.8'

services:
  postgres:
    image: postgres:latest
    environment:
      POSTGRES_USER: ${POSTGRES_USER}
      POSTGRES_PASSWORD: ${POSTGRES_PASSWORD}
      POSTGRES_DB: ${POSTGRES_DB}
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data

  mysql:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_ROOT_PASSWORD}
      MYSQL_DATABASE: ${MYSQL_DATABASE}
      MYSQL_USER: ${MYSQL_USER}
      MYSQL_PASSWORD: ${MYSQL_PASSWORD}
    ports:
      - "3306:3306"
    volumes:
      - mysql_data:/var/lib/mysql

volumes:
  postgres_data:
  mysql_data:
```

## Troubleshooting

If you encounter any issues, check the logs of the services using:
```sh
docker-compose logs
```

For more detailed information, refer to the official documentation of Docker and Docker Compose.