## Docker Commands Cheat Sheet

## Images

### List all local images
```bash
docker images
```

### Delete an image
```bash
docker rmi <image_name>
```

### Remove unused images
```bash
docker image prune
```

### Build an image
```bash
# Basic build
docker build -t <image_name>:<version> .

# Build without cache
docker build -t <image_name>:<version> . --no-cache
```

---

## Containers

### List containers
```bash
# All containers (running & stopped)
docker ps -a

# Running containers only
docker ps
```

### Create & run containers
```bash
# Basic run
docker run <image_name>

# Run in background
docker run -d <image_name>

# Custom name
docker run --name <container_name> <image_name>

# Port binding
docker run -p <host_port>:<container_port> <image_name>

# Set environment variables
docker run -e <var_name>=<var_value> <image_name>
```

### Manage containers
```bash
# Start/Stop
docker start|stop <container_name_or_id>

# Inspect details
docker inspect <container_name_or_id>

# Delete container
docker rm <container_name_or_id>
```

---

## Troubleshooting

### View logs
```bash
docker logs <container_name_or_id>
```

### Access container shell
```bash
docker exec -it <container_name_or_id> /bin/bash
docker exec -it <container_name_or_id> sh
```

---

## Docker Hub

### Image management
```bash
# Pull image
docker pull <image_name>

# Push image
docker push <username>/<image_name>

# Search images
docker search <image_name>
```

### Authentication
```bash
# Login
docker login -u <username>

# Logout
docker logout
```

---

## Volumes

### Manage volumes
```bash
# List volumes
docker volume ls

# Create/Delete
docker volume create <volume_name>
docker volume rm <volume_name>

# Mount volumes
docker run --volume <volume_name>:<mount_path> <image_name>
docker run --mount type=volume,src=<volume_name>,dest=<mount_path> <image_name>

# Cleanup
docker volume prune
```

---

## Networks

### Network management
```bash
# List networks
docker network ls

# Create/Remove
docker network create <network_name>
docker network rm <network_name>

# Cleanup
docker network prune
```
