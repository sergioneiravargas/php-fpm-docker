# PHP-FPM Docker environment
This environment comes with PHP-FPM 7.4, Nginx, MySQL 5.7 and Adminer containers.

By default, the containers are part of the **app** Docker **network**, it **must be created** before attempting to start the containers.

Custom configuration for PHP and Nginx should be set in the files from **docker/php/** and **docker/nginx/** directories.


## Start containers 
**Docker Compose** is **required**. Choose one of the following two methods to create and start the containers:

### Method 1 (inline vars)

Run the following command (replace the variable values first):
```
COMPOSE_NAME=your_var_value NGINX_PORT=your_var_value ADMINER_PORT=your_var_value /usr/local/bin/docker-compose -f docker-compose.yaml up -d
```

### Method 2 (.env file)
Create a **.env** file with this template:
```
COMPOSE_NAME=your_var_value
NGINX_PORT=your_var_value
ADMINER_PORT=your_var_value
```

Replace the variable values and run:
```
sudo docker-compose -f docker-compose.yaml --env-file .env up -d
```
