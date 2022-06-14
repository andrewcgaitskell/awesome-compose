# Introduction

This shows how to create a jupyterhub using podman

## change in to app folder

cd /jupyterhub

## create image from Dockefile

podman build -t my-jupyterhub-1 .

## create pod

podman run -dt --pod new:hub1 -p 8000:8000 localhost/my-jupyterhub-1:latest

## start pod

podman pod start hub1

## visit

http://35.214.57.82:8000/dev

## stop pod

podman pod stop hub1

## remove pod

podman pod rm hub1

## list all images

podman images

## remove all images

podman rmi -a

podman -rmi image-id

## list all containers

podman ps -a
