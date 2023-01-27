RUNNING KAFKA
---------------------------------------------------------------------

Running Kafka using docker image provided by Landoop.

```

https://hub.docker.com/r/landoop/fast-data-dev

```

This image provides a Kafka distribution with Apache Kafka, Kafka Connect, Zookeeper, Confluent Schema Registry and REST Proxy.

---------------------------------------------------------------------

Docker Compose YAML file:

```

version: '1'

services:
  # this is our kafka cluster.
  kafka-cluster:
    image: landoop/fast-data-dev:latest
    environment:
      ADV_HOST: 127.0.0.1         # Change to 192.168.99.100 if using Docker Toolbox
      RUNTESTS: 0                 # Disable Running tests so the cluster starts faster
      FORWARDLOGS: 0              # Disable running 5 file source connectors that bring application logs into Kafka topics
      SAMPLEDATA: 0               # Do not create sea_vessel_position_reports, nyc_yellow_taxi_trip_data, reddit_posts topics with sample Avro records.
    ports:
      - 2181:2181                 # Zookeeper
      - 3030:3030                 # Landoop UI
      - 8081-8083:8081-8083       # REST Proxy, Schema Registry, Kafka Connect ports
      - 9581-9585:9581-9585       # JMX Ports
      - 9092:9092                 # Kafka Broker

```

---------------------------------------------------------------------

Running with docker compose using detached mode:

```

docker-compose up -d

```

---------------------------------------------------------------------