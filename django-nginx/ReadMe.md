# Introduction

This shows how to create a django app using podman

# test with django app

## empty podman world

### stop pod

podman pod stop frontend

### remove pod

podman pod rm frontend

### list all images

podman images

### remove all images

podman rmi -a

## list all containers

podman ps -a

## change in to app folder

cd /django/app

## create image from Dockefile

podman build -t my-django-1 .

## create pod

podman run -dt --pod new:frontend -p 8080:80 localhost/my-django-1:latest

## start pod

podman pod start frontend

## visit

http://35.214.57.82:8080/

## stop pod

podman pod stop frontend

## remove pod

podman pod rm frontend

## list all images

podman images

## remove all images

podman rmi -a

podman -rmi image-id

## list all containers

podman ps -a
