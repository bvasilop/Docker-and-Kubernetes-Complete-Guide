# Docker Commands

* docker run hello-world
* docker run -d redis (Run a container as deamon, in * background)
* docker ps
* docker ps --all
* docker stop <containerId>
* docker kill <containerId>
* docker exec -it <containerId> <command>  (Ctrl + d to exit, * sh to enter shell)
* docker build .
* docker build -t <docker-user>/<image-name>:latest .
* docker build -f Dockerfile.dev . (Build from a arbitrary * file)
* docker system prune (delete all stopped containers and * build images)
* docker run -p 8080:8080 <imageName>
* docker run -p 3000:3000 -v /app/node_modules -v $(pwd):/app * <containerId>
*
* docker-compose up (docker run <image>)
* docker-compose up --build (docker build . && docker run * <image>)
* docker-copose up -deamon
* docker-compose down
* docker-compose ps (list runner containers from current directory with docker-compose.yml)