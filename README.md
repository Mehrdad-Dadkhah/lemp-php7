# lemp-php7
Docker compose file to run web server with nginx, mysql, redis, php7, phpmyadmin and ... with composer version 2.

it's a best and easiest way to up a complete development envirment with latest version of:

 - php 7
 - MySQL
 - Redis
 - PhpMyadmin
 - nginx
 - rabbitmq

##usage
if you have not install [docker at first install it](https://docs.docker.com/engine/installation/)
then [install docker-compose](https://docs.docker.com/compose/install/)
and finally in source directory (where docker-compose file is) run:

    docker-compose up -d

after run it you can use **phpmyadmin** on:
http://localhost:8080/

and login with
server name: db
user name: db_user
and password: 123456

if you want edit this configs you can edit this line in **docker-compose.yml** file:
- MYSQL_ROOT_PASSWORD=123456
    - MYSQL_PASSWORD=123456
    - MYSQL_DATABASE=docker_db
    - MYSQL_USER=db_user

**remember that you can change nginx config with edit default.conf file.**

if you want update them again you can use this commands:

    #to update mysql
    docker pull mysql
    
    #to update phpmyadmin
    docker pull phpmyadmin/phpmyadmin
    
    #to update php-redis
    docker pull redis
    
    #to update php7 and related extensions
    docker pull mehrdadkhah/php7
    
    #to update nginx
    docker pull nginx

**use composer**

docker exec php7 php composer.phar [command]