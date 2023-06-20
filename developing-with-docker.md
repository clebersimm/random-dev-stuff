### Python   

Create container do work with python/Django

Dockerfile
```yml
FROM python:3.11-slim

RUN python3 -m pip install Django

WORKDIR /home/python/app

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
