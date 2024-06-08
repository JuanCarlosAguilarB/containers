## Running PostgreSQL and pgAdmin with Docker
To run PostgreSQL using Docker, execute the following command:

```bash
docker run --name postgres-db -e POSTGRES_PASSWORD=your_password -e POSTGRES_USER=your_username -e POSTGRES_DB=your_database_name -p 5432:5432 -d postgres:latest
```
Replace your_password, your_username, and your_database_name with your desired values.

This command will start a PostgreSQL container with the specified environment variables and expose port 5432 on your local machine.

## pgAdmin
To run pgAdmin using Docker, execute the following command:

```bash
docker run --name pgadmin -e PGADMIN_DEFAULT_EMAIL=your_email@example.com -e PGADMIN_DEFAULT_PASSWORD=your_password -p 8080:80 -d dpage/pgadmin4
```
Replace your_email@example.com and your_password with your desired values.

This command will start a pgAdmin container and expose port 8080 on your local machine.

Once these containers are running, you can access pgAdmin via your web browser at http://localhost:8080 and connect it to the PostgreSQL server using the provided credentials.

## Running PostgreSQL and pgAdmin with Docker Compose
Docker Compose is a tool for defining and running multi-container Docker applications. With Docker Compose, you can define the services, networks, and volumes for your application in a YAML file, making it easy to manage and run multiple Docker containers as a single application.



Create a docker-compose.yml file in your project directory and add the following:

```yml
version: '3.7'

services:
  postgres-db:
    image: postgres:latest
    environment:
      POSTGRES_PASSWORD: your_password
      POSTGRES_USER: your_username
      POSTGRES_DB: your_database_name
    ports:
      - "5432:5432"

  pgadmin:
    image: dpage/pgadmin4
    environment:
      PGADMIN_DEFAULT_EMAIL: your_email@example.com
      PGADMIN_DEFAULT_PASSWORD: your_password
    ports:
      - "8080:80"

```

Replace your_password, your_username, your_database_name, your_email@example.com with your desired values.


### Running

To start PostgreSQL and pgAdmin containers using Docker Compose, navigate to the directory containing your docker-compose.yml file and execute the following command:

```bash
docker-compose up  

```
or
```bash
docker-compose up  -f ./postgres-docker-compose.yml

```


This command will create and start the containers defined in the docker-compose.yml file in detached mode, allowing you to continue using your terminal.

Once the containers are running, you can access pgAdmin via your web browser at http://localhost:8080 and connect it to the PostgreSQL server using the provided credentials.