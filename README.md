# PHP-RoadRunner
Docker image based on [php:7.4-cli-alpine](https://hub.docker.com/_/php?tab=tags&page=1&name=7.4-cli-alpine)
* Integrated [composer](https://roadrunner.dev/)
* Integrated php-extensions:
    * apcu
    * bcmath
    * curl
    * ctype
    * dom
    * iconv
    * json
    * intl
    * gd
    * mbstring
    * pcntl
    * pdo
    * pdo_pgsql
    * pgsql
    * posix
    * redis
    * session
    * simplexml
    * soap
    * sockets
    * timezonedb
    * xml
    * uuid
    * zip

### Usage

Basic `docker-compose.yml` example:
```yaml
services:
    php:
        image: cyradin/php:7.4-latest
        restart: always
        volumes:
            - .:/srv:rw
```
