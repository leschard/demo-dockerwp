# Demo path

## Initialize Docker Swarm

`docker swarm init`

## Get images

`docker pull wordpress`

`docker pull mysql:5.7`

## Build personalized WP image

`docker build -f Dockerfile-wordpress -t wp .`

## Deploy the stack

`docker stack deploy -c docker-compose.yml wp`

## Scaling demo

`docker service scale wp_wordpress=6`

## Image update

`docker service update wp_wordpress --image=wp`

## Kill container in prod

`docker kill <container_id>`
