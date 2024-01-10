### Containers   

"Production-ready, secure-by-design, ultra-small containers with chiselled Ubuntu"   
https://canonical.com/blog/chiselled-ubuntu-ga   

"Distroless images contain only your application and its runtime dependencies. They do not contain package managers, shells or any other programs you would expect to find in a standard Linux distribution"   
https://github.com/GoogleContainerTools/distroless   


### Python   

Create container do work with python/Django

Dockerfile
```yml
FROM python:3.11-slim

RUN python3 -m pip install Django

RUN groupadd -r pythondev -g 1000 && useradd -u 1000 -r -g pythondev

WORKDIR /home/python/app

EXPOSE 8000

CMD [ "tail","-f", "/dev/null"]
```

Control with docker-compose
docker-compose.yml
```yml
version: '3'

services:
  app:
    build: .
    volumes:
      - .:/home/python/app
    ports:
      - 8000:8000
```
Run docker compose up, can use -d, than run docker compose exec app bash

Script to access the container
```shell
#!/bin/bash
docker compose exec app bash
```

### GoLang
Dockerfile   
```yml
FROM golang:1.20

WORKDIR /home/go/app

CMD [ "tail","-f", "/dev/null"]
```

docker-compose.yml
```yml
version: '3'

services:
  app:
    build: .
    volumes:
      - .:/home/go/app
```
