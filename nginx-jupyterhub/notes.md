# Introduction

This shows how to create a jupyterhub using podman

## reset podman

podman system reset


## create nginx image

cd /nginx

podman build -t my-nginx-1 .

## change in to jupyterhub folder

cd ..

cd /jupyterhub

## create jupyterhub image from Dockefile

podman build -t my-jupyterhub-1 .

this takes a very long time

it is mainly the rebuild of jupyter lab

## create nginx pod

podman run -dt --pod new:hub1 -p 80:80 localhost/my-nginx-1:latest

# add image to pod

podman run -dt --pod hub1 localhost/my-jupyterhub-1:latest

## start pod

podman pod start hub1

## visit

http://35.214.57.82/dev

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
