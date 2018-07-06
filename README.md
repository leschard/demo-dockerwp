# Demo path

## Initialize Docker Swarm

`docker swarm init`

## Get images

`docker pull wordpress`

`docker pull mysql:5.7`

## Build personalized WP image

`docker build -f Dockerfile-wordpress -t wp .`

This modified version of the `wordpress` image imports a modified `security.conf` file that prevents the Apache server from including its software version (2.4.x) and the Linux distribution name (Debian) in the `Server` field of the HTTP header.

## Deploy the stack

`docker stack deploy -c docker-compose.yml wp`

## Scaling demo

`docker service scale wp_wordpress=6`

## Image update

`docker service update wp_wordpress --image=wp`

## Kill container in prod

`docker kill <container_id>`
