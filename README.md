# Great Job

---

## Build all project
turbo build

## Run all project
turbo start

---

# Project: map-web

## Build
turbo build --filter=map-web
turbo build:pre --filter=map-web
turbo build:prod --filter=map-web

## Run
turbo start --filter=map-web

## Run Dockerfile
docker build -f Dockerfile.map-web.dev -t map-web .
docker build -f Dockerfile.map-web.prod -t map-web .

---

# Docker Compose

## Run Docker-compose
docker-compose -p map-web -f docker-compose.dev.yml -p great-job up -d --build
docker-compose -p map-web -f docker-compose.pre.yml -p great-job up -d --build
docker-compose -p map-web -f docker-compose.prod.yml -p great-job up -d --build

---

# Push Docker Hub

## Project: map-web
docker tag map-web:latest hunizm/great-job-map-web:latest
docker push hunizm/great-job-map-web:latest
