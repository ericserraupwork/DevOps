# Docker

### Overview
Docker is an increasingly popular software package that creates a container for application development.

### Install
+ use below reference to install docker
    + `https://docs.docker.com/engine/install/ubuntu/`
    
### Command
+ `sudo docker system prune`   Command will remove all stopped containers.
+ `sudo docker container ls -a`  View all container
+ `sudo docker container rm ccsf3ff30ca cd25dkdk1` Remove selected docker container
+ `sudo docker image prune`

### Docker file sample
+ dockerfile for django
```dockerfile
# getting base image python3.7
FROM python:3.7-stretch
MAINTAINER wipitech <cowipitech@gmail.com>

# DateExplorer code lives here
WORKDIR /app

# DataExplorer dependencies
COPY requirement.txt .
RUN pip3 install -r requirement.txt

# DataExplorer source code
COPY . .

# Migrate DB
RUN python manage.py migrate

# DataExplorer listen below port
EXPOSE 8000

# Default to running with Gunicorn
CMD gunicorn Data_Explorer.wsgi -c gunicorn.py
```
+ dockerfile for kafka
```dockerfile
# getting base image python3.6
FROM python:3.7-stretch
MAINTAINER guixiao <guixiao417@gmail.com>

# 360notify code lives here
WORKDIR /app

## This requires librocksdb-dev>=5.0
#RUN apt-get install build-essential libsnappy-dev zlib1g-dev libbz2-dev libgflags-dev

# 360notify Python dependencies
COPY requirement.txt .
RUN pip3 install -r requirement.txt

# 360notify source code
COPY . .

# 360notify listen below ports
EXPOSE 9999 6066

# Run worker
CMD python -m app worker -l info
```

### Docker command to build and run
+ build docker image 
    + `sudo docker build -t docker_app:v1 .`
+ run docker image
    + `sudo docker run -it --rm --net host docker_app:v1`
    + `sudo docker run -d --rm --net host docker_app:v1`
        + Here `-it` means show log on terminal, `-d` means run docker in background mode
        + `--rm` remove previous image if it exists
        + `--net` set network method, it has `host`, `bridge`
        
    

