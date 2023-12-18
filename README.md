# Docker-environment-for-symfony

Use the master branch for a docker environment with PHP 8.3, MySql 8.2, the latest Redis and Nginx.

Use the develop branch to have Symfony 7.0.1 installed.

### Master

Add the gateway IP to the host machine's /etc/hosts file with the desired server name, 
then add that server name in docker/nginx/default.conf for the server_name attribute and in docker-compose
for the PHP_IDE_CONFIG. 

Lastly, edit docker/php/dockerfile and add your own email and name for git config.

docker compose up -d and the environment is ready for you to install what you need on it.

### Develop

Same as develop, just with a composer install in the php container to bring symfony up. 
