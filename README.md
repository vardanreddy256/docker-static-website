# Docker Static Website Project

This project demonstrates how to deploy a static website using Docker and Nginx.

## Technologies Used
- Docker
- Nginx
- Linux
- GitHub

## Project Structure

docker-static-website
│
├── Dockerfile
├── index.html
└── README.md


## Build Docker Image

docker build -t mywebsite .

## Run Docker Container

docker run -d -p 8080:80 mywebsite

## Access Website

http://localhost:8080
