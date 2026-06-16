## What is DevOps

## What is Docker
- Docker is a set of tools to deliver software in containers
- Containers are packages of software

## Benefits From containers

### Scenario 1: Work on my machine

* Application works on the developer's computer.
* Fails after deployment to the server.
* Caused by differences in dependencies, configurations, or software versions.
* Containers package the app with everything it needs to run.
* The same container runs consistently across development, testing, and production environments.
* Reduces environment-related issues and simplifies deployment.


### Scenario 2: Isolated Environments

* A server already runs an application using **Python 2.7**.
* Five new applications require **different Python versions**.
* Running them directly on the same system can cause **dependency conflicts**.
* **Containers isolate each application and its environment**.
* Each container includes its **own Python version and dependencies**.
* Applications run independently without affecting one another.
* Containers improve **compatibility, stability, and maintainability**.


### Scenario 3: Development

* A web application depends on services like **PostgreSQL, MongoDB, and Redis**.
* Installing and configuring each service manually is **time-consuming and complex**.
* Docker allows developers to **run these services in isolated containers**.
* Services can be started with **simple Docker commands**.
* Containers provide a **consistent and easy-to-manage development environment**.
* Reduces setup time and onboarding difficulties for new team members.


### Scenario 4: Scaling

* Docker containers start and stop **quickly**.
* Multiple container instances can be created to **handle increased traffic**.
* Traffic is distributed using **load balancing**.
* If one container fails, the **orchestration system detects the failure**.
* Traffic is redirected to **healthy containers**.
* A **new container is automatically started** to replace the failed one.
* Improves **scalability, availability, and reliability** of applications.

## Virtual Machines vs Containers 

* **VMs** include a full OS, run on a hypervisor, are heavier and slower but provide strong isolation.
* **Containers** share the host OS kernel, are lightweight, faster, and run only the app with dependencies.
* **VMs = full OS per instance**, **Containers = shared OS, isolated apps**.
* Docker depends on Linux kernel.

## Running Containers

* Run container:
  `docker container run hello-world`

* Docker pulls image if not found locally, then runs it.

* First run downloads image; next runs use local image.

* Check setup: output shows **"Hello from Docker!"**

* Be careful when running external images from the internet.

## Images and Containers

* **Image vs Container**

  * Image = blueprint (immutable file)
  * Container = running instance of an image

* **Metaphor**

  * Image = recipe
  * Container = cooked meal

* **Images**

  * Built using `Dockerfile`

    ```
    FROM <image>:<tag>
    RUN <install dependencies>
    CMD <command>
    ```
  * Build image: `docker image build`
  * List images: `docker image ls`

* **Containers**

  * Created from images
  * Can start, stop, interact
  * List running containers: `docker container ls` or `docker ps`
  * List all containers: `docker container ls -a`

* **Key idea**

  * One image → multiple containers


## Docker CLI Basics 
* Docker has 3 parts:

  * CLI client
  * REST API
  * Docker daemon

* Commands go like:

  * CLI → sends request → daemon handles containers/images

---

### Basic Image & Container Commands

* Run container:
  `docker container run <image>`
  or `docker run <image>`

* Pull image only:
  `docker image pull hello-world`

* List images:
  `docker image ls`

* List containers:

  * Running: `docker container ls` or `docker ps`
  * All: `docker container ls -a`

---

### Removing Containers & Images

* Remove container:
  `docker container rm <id/name>`

* Remove image:
  `docker image rm <image>`

* Error happens if container uses image → remove container first

* Stop running container:
  `docker container stop <name/id>`

---

### Bulk Cleanup

* Remove stopped containers:
  `docker container prune`

* Remove unused images:
  `docker image prune`

* Clean everything:
  `docker system prune`

---

### Detached Mode

* Run in background:
  `docker run -d nginx`

* Check running containers:
  `docker container ls`

* Stop container:
  `docker container stop <name>`

* Force remove:
  `docker container rm --force <name>`

---

### Key Idea

* Containers must be **stopped before removal**
* Docker system can accumulate unused images/containers over time


## Docker CLI 

* Stop container:
  `docker container stop blissful_wright`

* Remove container:
  `docker container rm blissful_wright`

* Force remove (if needed):
  `docker container rm --force blissful_wright`

* You can use **container name or ID (or partial ID)**

* Docker system can get cluttered with unused containers and images over time

---

### Most Used Docker Commands

| Command                             | Explanation                  | Shorthand       |
| ----------------------------------- | ---------------------------- | --------------- |
| `docker image ls`                   | List all images              | `docker images` |
| `docker image rm <image>`           | Remove image                 | `docker rmi`    |
| `docker image pull <image>`         | Download image               | `docker pull`   |
| `docker container ls -a`            | List all containers          | `docker ps -a`  |
| `docker container run <image>`      | Run container                | `docker run`    |
| `docker container rm <container>`   | Remove container             | `docker rm`     |
| `docker container stop <container>` | Stop container               | `docker stop`   |
| `docker container exec <container>` | Run command inside container | `docker exec`   |

---

### Key Idea

* Same commands work with **container name or ID**
* Shorthands are just **shorter versions of full commands** (some are legacy but still widely used)




