https://devopscube.com/podman-tutorial-beginners/

https://www.tecmint.com/manage-containers-using-podman-in-rhel/


podman run --name docker-nginx -p 80:80 docker.io/nginx
Error: rootlessport cannot expose privileged port 80, you can add 'net.ipv4.ip_unprivileged_port_start=80' to /etc/sysctl.conf (currently 1024), or choose a larger port number (>= 1024): listen tcp 0.0.0.0:80: bind: permission denied

need sudo for : podman run --name docker-nginx -p 80:80 docker.io/nginx

podman  run --name docker-nginx -p 8080:80 docker.io/nginx

## list images

podman images

## list all containers

podman ps -a

## stop container

podman stop container-id

podman rm container-id

## remove all containers

podman rm -a

## remove all images

podman rmi -a

## remove images

podman -rmi image-id

## create image from Dockerfile

podman build -t my-image-1 .

## create pod with above image

podman run -dt --pod new:frontend -p 8080:80 nginx

# test with flask app

## create image from Dockefile

podman build -t my-flask-1 .

## create pod

podman run -dt --pod new:frontend -p 8080:80 localhost/my-flask-1:latest

## start pod

podman pod start frontend

## visit

http://35.214.57.82:8080/

# create and manage pods

## create empty pod


