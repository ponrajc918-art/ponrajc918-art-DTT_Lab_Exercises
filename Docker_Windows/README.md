# Experiment 3 — Installing Docker and Executing Docker Commands on Windows

## Aim
To install and verify Docker on Windows, download Docker images, create and run containers, inspect containers and images, and practise basic container-management commands.

## Environment
- Operating system: Windows
- Docker Desktop with WSL 2 backend
- Docker CLI: 29.7.2
- Ubuntu image: `ubuntu:latest`
- Test image: `hello-world:latest`

## Procedure and Commands

### 1. Verify Docker installation
```cmd
docker --version
docker info
```

### 2. Download and run the Hello World image
```cmd
docker pull hello-world
docker images
docker run hello-world
```

**Observed result:** The container printed `Hello from Docker!` and exited successfully with status `Exited (0)`.

### 3. Download and run Ubuntu interactively
```cmd
docker pull ubuntu
docker run -it ubuntu bash
```

Inside the Ubuntu container, the following commands were tested:
```bash
cat /etc/os-release
pwd
ls
exit
```

**Observed result:** The Ubuntu shell opened successfully, system information and the root directory were inspected, and `exit` returned to Windows CMD.

### 4. List containers
```cmd
docker ps
docker ps -a
```

- `docker ps` lists running containers.
- `docker ps -a` lists running and stopped containers.

### 5. Stop and remove a container
```cmd
docker run -dit --name ubuntu-lab ubuntu bash
docker ps
docker stop ubuntu-lab
docker ps -a
docker rm ubuntu-lab
docker ps -a
```

The `ubuntu-lab` container was started, stopped, and removed successfully. The earlier stopped Ubuntu container named `relaxed_cori` was also removed.

### 6. Remove the Ubuntu image and verify
```cmd
docker rmi ubuntu:latest
docker images
docker ps -a
```

**Final verification:** The Ubuntu image and Ubuntu containers were removed. The `hello-world:latest` image remained available, and its completed container showed `Exited (0)`.

## Result
Docker was installed and verified on Windows. Images were downloaded and executed, an Ubuntu container was explored interactively, container and image listing commands were tested, and container stop/removal and image removal operations were completed successfully.
