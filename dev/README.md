# Local development

## Start local Postgress database

A PostgreSQL Docker container has been set up to facilitate local development. After navigating to the `dev/` directory, this container can be set up as follows:

### 1. Obtain SSL Certificates

For secure SSL communication, you need a pair of SSL certificates: `server.crt` and `server.key`. You can generate self-signed certificates by using OpenSSL:

```source-shell
openssl req -x509 -newkey rsa:4096 -keyout server.key -out server.crt -days 365 -nodes -subj "/CN=localhost"
```

Please note that this generates self-signed certificates which should only be used for local development.

### 2. Build the Docker image

```source-shell
docker build -t my_postgres_image -f Dockerfile.local-postgres .
```

This command will build the Docker image using the Dockerfile in the current directory. The previously generated SSL certificates will need to be in the same directory as the Dockerfile.

### 3. Run the Docker container

```source-shell
docker run --name my_postgres_container -p 25060:5432 -d my_postgres_image:latest
```

This command will start a new Docker container named my_postgres_container, mapping port 25060 on your local machine to port 5432 on the Docker container.

## Credit

This Docker setup is based on the [open-sauced/api](https://github.com/open-sauced/api/tree/09f37a29d0f4b9606fc57efe471725fd9040baba#%EF%B8%8F-setting-up-a-postgresql-database-locally)
