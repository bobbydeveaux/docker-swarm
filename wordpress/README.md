# Manual Wordpress Overlay Network with Swarm

```
docker swarm init
docker network create --driver overlay wpnet
docker service create --env MYSQL_ROOT_PASSWORD=password --env MYSQL_DATABASE=wordpress --network wpnet --replicas 1 --name wpdb mysql:latest
docker service create --env WORDPRESS_DB_HOST=wpdb --env WORDPRESS_DB_PASSWORD=password --network wpnet -p 80:80/tcp --name wpweb wordpress:latest
```

# Local Development for Wordpress
```
docker-compose up
```

# Bundle & Deployment with Docker services
```
docker-compose bundle
docker deploy -f docker.dsb myapp
docker service update -p 80:80 wp_web
```