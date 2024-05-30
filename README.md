# Kafka Cluster starter

Usage: `docker compose up`

This sets up:

- a single node Kafka cluster
- kafka-ui (localhost:9100)

## Kafka

Note that there's no need for Zookeeper (deprecated from Kafka 3.5.0).

- Port 9092 - from within the docker container network (host kafka0)
- Port 2902 - from the host network (host localhost)

From spring-boot, use these properties:

development profile:

```
spring.kafka.bootstrap-servers=localhost:29092
spring.kafka.consumer.group-id=myGroup
```

production (docker container) profile:

```
spring.kafka.bootstrap-servers=kafka0:9092
spring.kafka.consumer.group-id=myGroup
```


