# Docker-PHP7

A quick and easy way to setup your PHP application using Docker and docker-compose. This will setup a developement environment with PHP7-fpm, Xdebug and Nginx.

## Usage
~~~
git clone git@github.com:achrafSallemi/docker-php7-xdebug-nginx.git
cd docker-php7-xdebug-nginx
docker-compose up -d
~~~

### Structure

~~~
├── app
│   └── public
│       └── index.php
├── docker-compose.yml
├── fpm
│   ├── Dockerfile
│   └── supervisord.conf
├── nginx
│   ├── Dockerfile
│   └── default.conf
~~~

- `app` is the directory for project files. Put your files there.
- `Nginx` config is pointing to `app/public`, which can be changed in `nginx/default.conf`
- `Xdebug` is installed.


### Xdebug setup
- Change your IP address(use `ifconfig`command) on `xdebug.remote_host` value in `fpm/Dockerfile`
- Change your listening port to `9001` on Phpstorm
- Just create a remote debug server called `docker` (as mentionned on `docker-compose.yml` file = `PHP_IDE_CONFIG: serverName=docker`) on PHPSTORM and map the `app/public/` foler to `/var/app/public`
