# LEMP Overlay Network with Swarm

```
docker swarm init
```

# Local Development
This is just for local dev, if you want to shove your test scripts in the ./code dir
```
docker-compose build
docker-compose -f docker-compose.yml -f dev.yml up
```

# Bundle & Deployment with Docker services
```
docker
docker-compose bundle
docker deploy -f lemp.dsb lemp
docker service update -p 80:80 lemp_web
```

# Scale the php-fpm instances
docker service scale lemp_php-fpm=5

Access localhost and notice how the php-fpm nodes are auto load balanced by the Swarm. How awesome, eh?