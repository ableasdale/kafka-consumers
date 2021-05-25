# kafka-consumers

Sample Kafka Consumers

## Start Docker Compose

```
docker-compose up
```

## Connect to the `broker` container

```
docker-compose exec broker bash
kafka-topics --create --topic input-topic --bootstrap-server broker:9092 --replication-factor 1 --partitions 1
kafka-console-producer --topic input-topic --bootstrap-server broker:9092
```

## Enter some text

```
the quick brown fox
jumped over
the lazy dog
Go to Kafka Summit
All streams lead
to Kafka
```

## Building

```
./gradlew shadowJar
```

## Running

```
java -jar build/libs/kafka-consumer-application-standalone-0.0.1.jar configuration/dev.properties
```

## Check the output file

```
cat consumer-records.out
```

### Further Reading

https://kafka-tutorials.confluent.io/creating-first-apache-kafka-consumer-application/kafka.html