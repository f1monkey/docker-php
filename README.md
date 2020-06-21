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
* Install [RoadRunner](https://github.com/spiral/roadrunner) composer package
* Create `.rr.yaml` and `.rr.dev.yaml` in your project root (i.e. install [Roadrunner Bundle](https://github.com/Baldinof/roadrunner-bundle) for Symfony and use its config files)

Basic `docker-compose.yml` example:
```yaml
services:
    php:
        image: cyradin/php:7.4-latest
        restart: always
        volumes:
            - .:/srv:rw
```
`docker-compose.yml` example with wait-for-it:
```yaml
services:
    php:
        image: cyradin/php:7.4-latest
        environment:
            DEV_MODE: 1 # 1 - start "dev" server which uses .rr.dev.yaml, 0 - start "prod" server
            WAIT_FOR_HOST: postgres # url or docker container name to check for availability
            WAIT_FOR_PORT: 5432 # port to check for availability
            WAIT_FOR_TIMEOUT: 30 # Seconds to wait, default 30
        restart: always
        volumes:
            - .:/srv:rw
```