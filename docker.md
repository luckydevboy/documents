# Image

List all images:

```
docker images
```

Build an image from a Dockerfile:

```
docker build -t <image-name> <path-to-dockerfile>
```

Remove an image:

```
docker rmi <image-name>
```

# Container


Run a container from an image and persist data:

```
docker run -d -p <host-port>:<container-port> -v <host-path>:<container-path> <image-name>
```

List all running containers:

```
docker ps
```

List all stopped containers:

```
docker ps -a
```

Inspect a container:

```
docker inspect <container-id>
```

Stop a running container:

```
docker stop <container-id>
```

Remove a container:

```
docker rm <container-id>
```

Run a command in a running container:

```
docker exec -it <container-id> <command>
```

# Volume

Create a volume:

```
docker volume create <volume-name>
```

List all volumes:

```
docker volume ls
```

Inspect a volume:

```
docker volume inspect <volume-name>
```

Remove a volume:

```
docker volume rm <volume-name>
```

# Network

List all networks:

```
docker network ls
```

Create a network:

```
docker network create <network-name>
```

Remove a network:

```
docker network rm <network-name>
```

# Docker Compose

Create a docker-compose.yml file:

```
version: '3'
services:
  web:
    build: .
    ports:
      - 8000:8000
    volumes:
      - .:/code
    depends_on:
      - db
  db:
    image: postgres
    restart: always
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
      POSTGRES_DB: postgres
    volumes:
      - postgres_data:/var/lib/postgresql/data
volumes:
  postgres_data:
```

Start the containers:

```
docker-compose up -d
```

Stop the containers:

```
docker-compose down
```

# Docker Hub

Login to Docker Hub:

```
docker login
```

Push an image to Docker Hub:

```
docker push <image-name>
```
