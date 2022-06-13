
# test with nginx & flask app

## change in to app folder

cd /flask-nginx/app

## create image from Dockefile

podman build -t my-flask-1 .

podman build -t my-nginx-1 .

## create pod

podman run -dt --pod new:frontend localhost/my-flask-1:latest

## add image to pod

podman run -dt --pod frontend -p 8080:80 localhost/my-nginx-1:latest

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
