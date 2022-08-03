# PHP-FPM Docker environment
This environment comes with PHP-FPM 8.1, Nginx, MySQL 5.7 and Adminer containers.

Custom configuration for PHP and Nginx should be set in the files from **docker/php/** and **docker/nginx/** directories.

## **Start containers** 
**Docker Compose** is **required**. Choose one of the following two methods to create and start the containers:

### **Method 1 (inline vars)**
Run the following command (replace the variable values first):
```
COMPOSE_NAME={{ your value }} NGINX_PORT={{ your value }} ADMINER_PORT={{ your value }} docker compose -f docker/docker-compose.yaml up -d
```

### **Method 2 (.env file)**
Create a **docker/.env** file with this template:
```
COMPOSE_NAME={{ your value }}
NGINX_PORT={{ your value }}
ADMINER_PORT={{ your value }}
```

Replace the variable values and run:
```
docker compose -f docker/docker-compose.yaml --env-file docker/.env up -d
```
