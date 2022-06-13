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

## remove images

podman -rmi image-id

# create and manage pods

## create empty pod


