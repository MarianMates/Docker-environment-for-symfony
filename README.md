# Docker-environment-for-symfony

Use the master branch for a docker environment with PHP 8.3, MySql 8.2, the latest Redis and Nginx.

Use the develop branch to have Symfony 7.0.1 installed.

### Master

Add the gateway IP (172.20.0.1 by default) to the host machine's /etc/hosts file with the desired server name (symfony.local by default), 
then add that server name in docker/nginx/default.conf for the server_name attribute and in docker-compose
for the PHP_IDE_CONFIG. 

Lastly, edit docker/php/dockerfile and add your own email and name for git config.

docker compose up -d and the environment is ready for you to install what you need on it.

### Develop

Same as master, just with a composer install in the php container to bring symfony up. 

### XDebug
XDebug needs a server configuration in PhpStorm in order to work. For this, go to 
PhpStorm -> Settings -> PHP -> Servers and add a new server with the following configurations :
- Name : whatever you added as the server name in the nginx config and hosts file
- Host : the gateway IP
- Check "Use path mappings"
- On the "Absolute path on the server" column, add "/var/www/symfony" next to the local project path (Project files).

Apply and OK.