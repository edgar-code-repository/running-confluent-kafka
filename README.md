RUNNING CONFLUENTE KAFKA 5.3
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
