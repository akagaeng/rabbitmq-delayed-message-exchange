# rabbitmq-delayed-message-exchange

## Overview

This image contains:
* RabbitMQ 3.8.3
* RabbitMQ Plugin: rabbitmq_management
* RabbitMQ Plugin: rabbitmq_delayed_message_exchange for 3.7.x / 3.8.x

## How to use

### Sample usage

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

#### Open rabbitmq management

- Open http://localhost:8080/ on your browser
- Login with `rabbit` / `rabbit`

## References
* [RabbitMQ Official images](https://hub.docker.com/_/rabbitmq)
* [RabbitMQ Delayed Message Exchange Plugin](https://www.rabbitmq.com/community-plugins.html)