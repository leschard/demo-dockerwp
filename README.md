# Demo path

## Deploy the stack

`docker stack deploy -c docker-compose.yml wp`

## Scaling demo

`docker service scale wp_wordpress=6`

## Image update

`docker service update wp_wordpress --image=wp`

## Kill container in prod

`docker kill <container_id>`
