# Important Docker Commands

# Introduction to My Docker Presentation

Hello! My name is **Hossein Hosseini**, and I am excited to present on **Docker** today. This presentation is part of my coursework in the **Cloud Computing** course at the **University of Isfahan**. 

- **Presentation Date**: October 7, 2024
- **Instructor**: Dr. Masoreheh Ejei
- **Term**: 403-01 (First Term of the 403-404 Academic Year)

In this presentation, we will explore the fundamental concepts of Docker, including its architecture, key commands, and practical applications. The following sections will provide detailed explanations and examples that complement my talk.

This markdown file serves as a comprehensive guide, helping you to better understand Docker and its significance in cloud computing. I hope you find it useful as we dive into the world of containerization!

این دستورات عملکردهای اساسی مورد نیاز برای کار با کانتینرها، ایمیج، ولوم‌ها، شبکه‌ها و دیگر اجزای داکر را پوشش می‌دهند. شنایی با این دستورات به شما کمک می‌کند تا برنامه‌های Dockerized را به‌طور مثر بسازید، مستقر کنید و مدیریت کنید.


## Installing Docker on Various Operating Systems

1. **Linux**:
   - **Installation**:
     - Basic commands:
       ```bash
       sudo apt-get update
       sudo apt-get install docker-ce
       ```
   - **Configuration**:
     - Enable Docker to start on boot:
       ```bash
       sudo systemctl enable docker
       ```

2. **Windows**:
   - **System Requirements**:
     - Windows 10 (Pro, Enterprise, or Education) 64-bit with Hyper-V enabled.
   - **Installation Steps**:
     - Download the Docker Desktop installer from the [Docker Hub](https://hub.docker.com/).
     - Run the installer and follow the prompts to enable necessary features like Hyper-V.
     - Restart your computer after installation.

## Basic Docker Commands
- **Pull an image**:
  ```bash
  docker pull <image-name>
  ```
- **Run a container**:
  ```bash
  docker run <image-name>
  ```
- **Stop a container**:
  ```bash
  docker stop <container-id>
  ```
- **Remove a container**:
  ```bash
  docker rm <container-id>
  ```

## General Commands

### Check Docker Version

```bash
docker --version
```

Displays the installed Docker version.

نسخه نصب شده داکر را نمایش می‌دهد.

### Display System-Wide Information

```bash
docker info
```

Shows detailed information about the Docker installation.

اطلاعات جامع درباره نصب داکر را نشان می‌دهد.

## Images Management

### List Local Docker Images

```bash
docker images
```

Lists all Docker images stored locally.

تمام ایمیج داکر ذخیره شده به صورت محلی را فهرست می‌کند.

### Search for an Image on Docker Hub

```bash
docker search <image_name>
```

Searches Docker Hub for images matching `<image_name>`.

دنبال ایمیج مطابق با `<image_name>` در Docker Hub می‌گردد.

### Pull an Image from Docker Hub

```bash
docker pull <repository>/<image_name>:<tag>
```

Downloads an image from Docker Hub. If no tag is specified, the `latest` tag is used by default.

یک ایمیچ را از Docker Hub دانلود می‌کند. اگر تگ مشخص نشود، به‌طور پیش‌فرض از تگ `latest` استفاده می‌شود.

### Remove a Docker Image

```bash
docker rmi <image_name>:<tag>
```

Deletes a local image. Use the image ID or name.

یک ایمیچ محلی را حذف می‌کند. می‌توان از ID یا نام ایمیچ استفاده کرد.

### Tag an Image

```bash
docker tag <existing_image> <new_repository>/<new_image>:<new_tag>
```

Creates a new tag for an image.

یک تگ جدید برای ایمیچ ایجاد می‌کند.

### Push an Image to a Registry

```bash
docker push <repository>/<image_name>:<tag>
```

Uploads an image to a Docker registry.

یک ایمیچ را به رجیستری داکر آپلود می‌کند.

### Build an Image from a Dockerfile

```bash
docker build -t <image_name>:<tag> <path_to_dockerfile_directory>
```

Builds a new image from a specified directory containing a `Dockerfile`.

یک ایمیچ جدید از دایرکتوری مشخص شده که شامل `Dockerfile` است، می‌سازد.

### Display Image History

```bash
docker history <image_name>:<tag>
```

Shows the history of an image's layers.

تاریخچه لایه‌های یک ایمیچ را نشان می‌دهد.

## Containers Management

### List Running Containers

```bash
docker ps
```

Displays all currently running containers.

تمام کانتینرهای در حال اجرا را نمایش می‌دهد.

### List All Containers

```bash
docker ps -a
```

Shows all containers, including those that are stopped.

همه کانتینرها، از جمله کانتینرهای متوقف شده را نشان می‌دهد.

### Create and Run a Container

```bash
docker run <image_name>
```

Creates and starts a container from an image.

از یک ایمیچ، کانتینری را ایجاد و اجرا می‌کند.

#### Run a Container in Detached Mode

```bash
docker run -d <image_name>
```

Starts a container in the background (detached).

کانتینر را در پس‌زمینه (حالت جدا شده) اجرا می‌کند.

#### Map Ports

```bash
docker run -p <host_port>:<container_port> <image_name>
```

Maps a container port to a port on the host machine.

یک پورت کانتینر را به پورتی در ماشین میزبان متصل می‌کند.

#### Name a Container

```bash
docker run --name <container_name> <image_name>
```

Assigns a custom name to the container.

یک نام سفارشی به کانتینر اختصاص می‌دهد.

#### Set Environment Variables

```bash
docker run -e <KEY>=<VALUE> <image_name>
```

Sets environment variables inside the container.

متغیرهای محیطی را درون کانتینر تنظیم می‌کند.

#### Mount a Volume

```bash
docker run -v <host_path>:<container_path> <image_name>
```

Mounts a host directory or volume into the container.

یک دایرکتوری میزبان یا ولوم را به کانتینر متصل می‌کند.

### Start a Stopped Container

```bash
docker start <container_id_or_name>
```

Starts a container that was previously stopped.

یک کانتینر متوقف شده را راه‌اندازی می‌کند.

### Stop a Running Container

```bash
docker stop <container_id_or_name>
```

Stops a running container gracefully.

یک کانتینر در حال اجرا را به‌صورت ایمن متوقف می‌کند.

### Restart a Container

```bash
docker restart <container_id_or_name>
```

Restarts a container.

کانتینر را مجددا راه‌اندازی می‌کند.

### Remove a Container

```bash
docker rm <container_id_or_name>
```

Deletes a container. Containers must be stopped before removing.

کانتینر را حذف می‌کند. قبل از حذف، کانتینر باید متوقف شود.

### Force Remove a Running Container

```bash
docker rm -f <container_id_or_name>
```

Stops and removes a container in a single command.

در یک فرمان، کانتینر را متوقف و حذف می‌کند.

### Run a Command in a Running Container

```bash
docker exec -it <container_id_or_name> <command>
```

Executes a command inside a running container. The `-it` flags run it interactively.

یک فرمان را داخل کانتینر در حال اجرا، اجرا می‌کند. گزینه‌های `-it` اجرای تعاملی را فراهم می‌کنند.

#### Start a Bash Shell in a Container

```bash
docker exec -it <container_id_or_name> /bin/bash
```

Provides an interactive Bash shell inside the container.

یک شل Bash تعاملی در داخل کانتینر فراهم می‌کند.

### View Container Logs

```bash
docker logs <container_id_or_name>
```

Displays the logs of a container.

لاگ‌های کانتینر را نمایش می‌دهد.

#### Follow Logs in Real-Time

```bash
docker logs -f <container_id_or_name>
```

Streams the container logs in real-time.

لاگ‌های کانتینر را به‌صورت زنده دنبال می‌کند.

### Inspect a Container

```bash
docker inspect <container_id_or_name>
```

Shows detailed information about a container in JSON format.

اطلاعات دقیق درباره کانتینر را در قالب JSON نشان می‌دهد.

### Display Running Processes in a Container

```bash
docker top <container_id_or_name>
```

Lists the processes running inside a container.

فریندهای در حال اجرا داخل کانتینر را فهرست می‌کند.

### Monitor Resource Usage

```bash
docker stats
```

Shows a live stream of container(s) resource usage statistics.

آمار لحظه‌ای استفاده از منابع کانتینر(ها) را نمایش می‌دهد.

### Copy Files from Container to Host

```bash
docker cp <container_id_or_name>:<container_path> <host_path>
```

Copies files or directories from the container's filesystem to the host.

فایل‌ها یا دایرکتوری‌ها را از فایل‌سیستم کانتینر به میزبان کپی می‌کند.

### Copy Files from Host to Container

```bash
docker cp <host_path> <container_id_or_name>:<container_path>
```

Copies files or directories from the host to the container's filesystem.

فایل‌ها یا دایرکتوری‌ها را از میزبان به فایل‌سیستم کانتینر کپی می‌کند.

### Commit a Container to an Image

```bash
docker commit <container_id_or_name> <new_image_name>:<tag>
```

Creates a new image from a container's changes.

یک ایمیچ جدید از تغییرات کانتینر ایجاد می‌کند.

### Rename a Container

```bash
docker rename <old_name> <new_name>
```

Changes the name of a container.

نام یک کانتینر را تغییر می‌دهد.

### Pause a Container

```bash
docker pause <container_id_or_name>
```

Suspends all processes in a container.

تمام فریندهای درون کانتینر را متوقف می‌کند.

### Unpause a Container

```bash
docker unpause <container_id_or_name>
```

Resumes all processes in a paused container.

تمام فریندهای کانتینر متوقف شده را ادامه می‌دهد.

### Kill a Container

```bash
docker kill <container_id_or_name>
```

Stops a container immediately by sending a `SIGKILL` signal.

با ارسال سیگنال `SIGKILL`، کانتینر را فورا متوقف می‌کند.

### Update Container Resource Limits

```bash
docker update --cpus=<value> --memory=<value> <container_id_or_name>
```

Updates resource constraints on a running container.

محدودیت‌های منابع یک کانتینر در حال اجرا را به‌روز می‌کند.

### Run a Container and Remove It After Exit

```bash
docker run --rm <image_name>
```

Automatically removes the container when it exits.

پس از خروج، کانتینر را به‌طور خودکار حذف می‌کند.

## Volumes Management

### List Volumes

```bash
docker volume ls
```

Displays all Docker volumes.

تمام ولوم‌های داکر را نمایش می‌دهد.

### Create a Volume

```bash
docker volume create <volume_name>
```

Creates a new volume.

یک ولوم جدید ایجاد می‌کند.

### Remove a Volume

```bash
docker volume rm <volume_name>
```

Deletes a volume.

یک ولوم را حذف می‌کند.

### Inspect a Volume

```bash
docker volume inspect <volume_name>
```

Shows detailed information about a volume.

اطلاعات دقیق درباره یک ولوم را نشان می‌دهد.

### Prune Unused Volumes

```bash
docker volume prune
```

Removes all unused local volumes.

تمام ولوم‌های محلی بدون استفاده را حذف می‌کند.

## Networks Management

### List Networks

```bash
docker network ls
```

Shows all Docker networks.

تمام شبکه‌های داکر را نمایش می‌دهد.

### Create a Network

```bash
docker network create <network_name>
```

Creates a new network.

یک شبکه جدید ایجاد می‌کند.

### Remove a Network

```bash
docker network rm <network_name>
```

Deletes a network.

یک شبکه را حذف می‌کند.

### Connect a Container to a Network

```bash
docker network connect <network_name> <container_id_or_name>
```

Attaches a container to a network.

یک کانتینر را به یک شبکه متصل می‌کند.

### Disconnect a Container from a Network

```bash
docker network disconnect <network_name> <container_id_or_name>
```

Detaches a container from a network.

یک کانتینر را از یک شبکه جدا می‌کند.

### Inspect a Network

```bash
docker network inspect <network_name>
```

Provides detailed information about a network.

اطلاعات دقیق درباره یک شبکه را فراهم می‌کند.

### Prune Unused Networks

```bash
docker network prune
```

Removes all unused networks.

تمام شبکه‌های بدون استفاده را حذف می‌کند.

## System Commands

### Prune Unused Data

```bash
docker system prune
```

Cleans up unused containers, networks, images, and optionally, volumes.

کانتینرها، شبکه‌ها، ایمیج و در صورت نیاز ولوم‌های بدون استفاده را پاکسازی می‌کند.

#### Prune Everything

```bash
docker system prune -a
```

Removes all unused containers, networks, images (both dangling and unreferenced), and optionally, volumes.

همه کانتینرها، شبکه‌ها، ایمیج (هم شناور و هم بدون استفاده) و در صورت نیاز ولوم‌های بدون استفاده را حذف می‌کند.

### Display System Disk Usage

```bash
docker system df
```

Shows Docker disk usage.

استفاده دیسک توسط داکر را نمایش می‌دهد.

### Docker Registry

**Docker Registry** is a service for storing and distributing Docker images. It allows developers to store their images in a centralized location, making it easier to share images with teams and deploy applications across different environments.

#### Key Features of Docker Registry:
- **Private and Public Repositories**: Users can create both private and public repositories to manage their images.
- **Image Management**: It allows you to push (upload) and pull (download) images from the registry, manage versioning, and keep track of different image tags.
- **Custom Registries**: Organizations can set up their own Docker Registry on-premises for enhanced security and control over their images.

### Docker Hub

**Docker Hub** is the official public registry service provided by Docker. It hosts a vast library of pre-built images, making it easier for developers to find and use existing software images.

#### Key Features of Docker Hub:
- **Public Repositories**: Users can access thousands of public repositories to find images for popular applications and frameworks.
- **Automated Builds**: Docker Hub can automatically build images from source code stored in GitHub or Bitbucket repositories.
- **Integration with CI/CD**: It seamlessly integrates with continuous integration and deployment pipelines, allowing for streamlined workflows.
- **User Accounts**: Users can create accounts to manage their images, share with teams, and control access to their repositories.

### Conclusion

Both Docker Registry and Docker Hub play vital roles in the Docker ecosystem by facilitating image storage and distribution. While Docker Hub is a public service with a wide variety of images available, Docker Registry can be used for private storage solutions tailored to specific organizational needs.

For more detailed information, you can check out the official Docker documentation on [Docker Registry](https://docs.docker.com/registry/) and [Docker Hub Doc](https://docs.docker.com/docker-hub/) and [Docker Hub](https://hub.docker.com/).

### Login to a Docker Registry

```bash
docker login
```

Authenticates with a Docker registry (Docker Hub by default).

با یک رجیستری داکر احراز هویت می‌کند (پیش‌فرض Docker Hub است).

### Logout from a Docker Registry

```bash
docker logout
```

Logs out from a Docker registry.

از یک رجیستری داکر خارج می‌شود.

## Docker Compose Commands

### Start Services

```bash
docker-compose up
```

Builds, (re)creates, starts, and attaches to containers for services.

برای سرویس‌ها، کانتینرها را می‌سازد، (دوباره) ایجاد می‌کند، راه‌اندازی می‌کند و متصل می‌شود.

#### Start Services in Detached Mode

```bash
docker-compose up -d
```

Starts services in the background.

سرویس‌ها را در پس‌زمینه اجرا می‌کند.

### Stop Services

```bash
docker-compose down
```

Stops and removes containers, networks, images, and volumes.

کانتینرها، شبکه‌ها، ایمیج و ولوم‌ها را متوقف و حذف می‌کند.

### Build or Rebuild Services

```bash
docker-compose build
```

Builds images for services defined in a `docker-compose.yml` file.

ایمیج سرویس‌های تعریف شده در فایل `docker-compose.yml` را می‌سازد.

### List Services

```bash
docker-compose ps
```

Lists containers managed by Docker Compose.

کانتینرهای مدیریت شده توسط Docker Compose را فهرست می‌کند.

### View Compose Logs

```bash
docker-compose logs
```

Displays log output from services.

خروجی لاگ‌های سرویس‌ها را نمایش می‌دهد.

### Scale Services

```bash
docker-compose scale <service>=<number>
```

Sets the number of containers to run for a service.

تعداد کانتینرهای در حال اجرا برای یک سرویس را تنظیم می‌کند.

## Save and Load Images

### Save an Image to a Tar Archive

```bash
docker save -o <path_to_tar_file> <image_name>:<tag>
```

Exports an image to a tar file.

یک ایمیچ را به فایل tar صادر می‌کند.

### Load an Image from a Tar Archive

```bash
docker load -i <path_to_tar_file>
```

Imports an image from a tar file.

یک ایمیچ را از فایل tar وارد می‌کند.

## Export and Import Containers

### Export a Container's Filesystem

```bash
docker export -o <path_to_tar_file> <container_id_or_name>
```

Exports the filesystem of a container to a tar file.

فایل‌سیستم یک کانتینر را به فایل tar صادر می‌کند.

### Import a Filesystem as an Image

```bash
docker import <path_to_tar_file> <new_image_name>:<tag>
```

Creates an image from a tarball.

یک ایمیچ را از یک فایل tar ایجاد می‌کند.

## Context Management

In Docker, **context** refers to the set of files and directories that are used to build a Docker image. This includes the **Dockerfile** and any other files needed during the build process.

### Key Points about Docker Context:

1. **Image Creation**: When you run the `docker build` command, Docker uses the files in the context to create a new image.

2. **Path Specification**: The context is specified when running the `docker build` command. For example:
   ```bash
   docker build -t my-image .
   ```
   Here, `.` indicates that the context is in the current directory.

3. **File Transfer**: All files in the context are sent to the Docker daemon, so using a `.dockerignore` file to exclude unnecessary files can help optimize the build process.

4. **Size Considerations**: A large context can slow down the build process, so it's advisable to only include necessary files.

5. **Logical Structure**: Organizing your project structure to keep the context simple and efficient is best practice.


### List Docker Contexts

```bash
docker context ls
```

Shows all Docker contexts.

تمام کانتکست‌های داکر را نمایش می‌دهد.

### Use a Docker Context

```bash
docker context use <context_name>
```

Switches to a specified Docker context.

به یک کانتکست داکر مشخص سوی می‌کند.

### Create a Docker Context

```bash
docker context create <context_name>
```

Creates a new Docker context.

یک کانتکست داکر جدید ایجاد می‌کند.

## Advanced Commands

### Build an Image Without Cache

```bash
docker build --no-cache -t <image_name>:<tag> <path_to_dockerfile_directory>
```

Builds an image without using cache.

یک ایمیچ را بدون استفاده از کش می‌سازد.

### Run a Container with Custom CPU and Memory Limits

```bash
docker run --cpus=".5" --memory="256m" <image_name>
```

Limits the container's CPU usage to 50% and memory to 256MB.

استفاده CPU کانتینر را به  و حافظه را به MB محدود می‌کند.

### Specify Restart Policies for Containers

```bash
docker run --restart=always <image_name>
```

Automatically restarts the container if it exits.

در صورت خروج، کانتینر را به‌طور خودکار مجددا راه‌اندازی می‌کند.

### View Port Mappings of a Container

```bash
docker port <container_id_or_name>
```

Lists port mappings or a specific mapping for a container.

نگاشت‌های پورت کانتینر را لیست می‌کند.

### Attach to a Running Container

The command `docker attach <container_id_or_name>` is used to connect your terminal to a running Docker container's main process. Here’s a simplified breakdown:

- **Purpose**: It allows you to interact directly with the application running inside the container, such as sending commands or viewing output.

- **How to Use**:
  - Run the command:
    ```bash
    docker attach my_container
    ```
    This connects you to the container named `my_container`.

- **Detaching**: To exit without stopping the container, use `Ctrl + P`, then `Ctrl + Q`.

- **Important Notes**:
  - Only one terminal can be attached at a time.
  - This command connects you to the existing process, unlike `docker exec`, which opens a new shell session.


### Attach to a Running Container

```bash
docker attach <container_id_or_name>
```

Connects to a running container's main process.

به فرآیند اصلی یک کانتینر در حال اجرا متصل می‌شود.

## Docker Swarm Commands (Advanced)

### Initialize a Swarm

```bash
docker swarm init
```

Turns the current machine into a swarm manager.

ماشین فعلی را به یک مدیر Swarm تبدیل می‌کند.

### Join a Swarm

```bash
docker swarm join --token <token> <manager_ip>:<manager_port>
```

Adds a node to a swarm.

یک نود را به Swarm اضافه می‌کند.

### List Swarm Nodes

```bash
docker node ls
```

Displays all nodes in the swarm.

همه نودهای موجود در Swarm را نمایش می‌دهد.

### Deploy a Stack in Swarm Mode

```bash
docker stack deploy -c <compose_file> <stack_name>
```

Deploys a new stack or updates an existing stack.

یک Stack جدید را پیاده‌سازی یا یک Stack موجود را به‌روز می‌کند.

## Docker Secret Commands (Advanced)

### Create a Secret

```bash
docker secret create <secret_name> <secret_file>
```

Stores sensitive data in the swarm.

داده‌های حساس را در Swarm ذخیره می‌کند.

### List Secrets

```bash
docker secret ls
```

Lists secrets managed by Docker.

تمام Secret‌های مدیریت شده توسط داکر را فهرست می‌کند.

### Remove a Secret

```bash
docker secret rm <secret_name>
```

Deletes a secret.

یک Secret را حذف می‌کند.

---


## Utility Information

### The VPS:
| **Property**   | **Value**               |
|----------------|-------------------------|
| **IPv4**       | 87.107.155.76           |
| **SSH Port**   | 9011                    |
| **OS**         | Linux (Ubuntu 24.0)     |
| **Username**    | root                    |
| **Password**   | QNiuo2jsx0             |

### The DNS:

| **Property**   | **Value**               |
|----------------|-------------------------|
| **First IP**   | 87.107.155.76           |
| **Second IP**  | 9011                    |
| **URL**        | [403.online](https://403.online/)|

### The directory for set DNS in Ubuntu (netplan):
  
```bash
/etc/netplan/50-cloud-init.yaml
```

### Generating SSH Key on windows:
```bash
ssh-keygen -t rsa -b 4096 -C "{your-name}" -f C:\Users\Huseyn\.ssh\{key-name}
```