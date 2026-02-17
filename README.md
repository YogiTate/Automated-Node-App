# Automated Node App 
## Project Description
This is a Node.js application with a complete CI/CD pipeline using Docker, Jenkins, and GitHub. The application is containerized using Docker and deployed automatically.

## Technologies Used

* Node.js
* Docker
* Jenkins
* GitHub
* Docker Hub

## Docker Image

Docker Hub Link:
https://hub.docker.com/r/yogi93676/automated-node-app

## Run Application using Docker

Build image:

```
docker build -t yogi93676/automated-node-app .
```

Run container:

```
docker run -d -p 3000:3000 yogi93676/automated-node-app
```

Open browser:

```
http://localhost:3000
```

---

## Docker Container Screenshot

![Docker Screenshot](docs/docker-container.png)

<img width="1436" height="898" alt="docker-container" src="https://github.com/user-attachments/assets/04ccfb76-fc4b-4506-a50e-b820affed755" />

## CI/CD Pipeline Flow

GitHub → Jenkins → Docker → Docker Hub → Run Container

## Author

Bala Yogi
GitHub: https://github.com/YogiTate
