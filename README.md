RUNNING KAFKA CONFLUENT 5.3
---------------------------------------------------------------------


Useful note: 
command to kill a process that runs in a given port (in Ubuntu).

```

sudo kill -9 `sudo lsof -t -i:2181`

```

---------------------------------------------------------------------

**Execute Zookeeper**

```

bin/zookeeper-server-start etc/kafka/zookeeper.properties

```

---------------------------------------------------------------------

**Running Kafka Broker**


```

bin/kafka-server-start etc/kafka/server-0.properties
bin/kafka-server-start etc/kafka/server-1.properties
bin/kafka-server-start etc/kafka/server-2.properties

```

---------------------------------------------------------------------

**Creating and listing topics in Kafka**

This command allows you to create a topic in Kafka called "topic-example":

```

bin/kafka-topics --create --topic topic-example --partitions 3 --replication-factor 3 --bootstrap-server http://localhost:9092

```

Previous commando does not return anything.

Listing topics:

```
bin/kafka-topics --zookeeper localhost:2181 --list

```

Result after running the previous command:

```
__confluent.support.metrics
__consumer_offsets
_schemas
topic-example

```

---------------------------------------------------------------------


**Deleting and listing topics in Kafka**


Deleting a topic called "topic-example":
```

bin/kafka-topics --bootstrap-server localhost:9092 --delete --topic topic-example

```

Previous command does not return anything. 

Listing the topics again we can see the topic was deleted:

```
bin/kafka-topics --zookeeper localhost:2181 --list

__confluent.support.metrics
__consumer_offsets
_schemas

```

---------------------------------------------------------------------
