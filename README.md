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



