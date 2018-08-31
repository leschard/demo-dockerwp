# Demo path

## Fetch git content

```bash
git clone https://github.com/leschard/demo-dockerwp
```

## Initialize Docker Swarm

```bash
docker swarm init
```

## Get images

```bash
docker pull wordpress
docker pull mysql:5.7
```

## Build personalized WP image

```bash
docker build -f Dockerfile-wordpress -t wp .
```

This modified version of the `wordpress` image imports a modified `security.conf` file that prevents the Apache server from including its software version (2.4.x) and the Linux distribution name (Debian) in the `Server` field of the HTTP header.

## Deploy the stack

```bash
docker stack deploy -c docker-compose.yml wp
```

## Scaling demo

```bash
docker service scale wp_wordpress=6
```

## Image update

```bash
docker service update wp_wordpress --image=wp
```

## Kill container in prod

```bash
docker kill <container_id>
```
