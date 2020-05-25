# rabbitmq-delayed-message-exchange

## Overview

Hosted at docker hub 
* https://hub.docker.com/repository/docker/akagaeng/rabbitmq-delayed-message-exchange
* Automated build
  * Scenario: Match versions
  * Source type: Tag (git tag: `/^[0-9.]+$/`) e.g. `3.8.3`
  * Docker Tag: `{sourceref}` e.g. `3.8.3`

This image contains:
* RabbitMQ 3.8.3
* RabbitMQ Plugin: rabbitmq_management
* RabbitMQ Plugin: rabbitmq_delayed_message_exchange for 3.7.x / 3.8.x

## Usage

### Using docker

```
$ docker run -d \
        --name rabbitmq \
        -p 5672:5672 \
        -p 8080:15672 \
        -e RABBITMQ_DEFAULT_USER=rabbit \
        -e RABBITMQ_DEFAULT_PASS=rabbit \
        akagaeng/rabbitmq-delayed-message-exchange
```

### Using docker-compose

#### Create docker-compose.yaml

```
version: '3.3'
services:
    rabbitmq:
        container_name: rabbitmq
        ports:
            - '5672:5672'
            - '8080:15672'
        image: 'akagaeng/rabbitmq-delayed-message-exchange'
        environment:
            - RABBITMQ_DEFAULT_USER=rabbit
            - RABBITMQ_DEFAULT_PASS=rabbit
```

#### Run docker-compose

```
$ docker-compose up -d
```

### Open rabbitmq management

- Open http://localhost:8080/ in a browser
- Login with `rabbit` / `rabbit`

## Additional Configuration
- Visit [rabitmq official image hub](https://hub.docker.com/_/rabbitmq) 


## References
* [RabbitMQ Official images](https://hub.docker.com/_/rabbitmq)
* [RabbitMQ Delayed Message Exchange Plugin](https://www.rabbitmq.com/community-plugins.html)