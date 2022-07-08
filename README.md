# Kafka-Connect
 ##To run the Kafka Cluster
 1. /bin/zookeeper-server-start ./etc/kafka/zookeeper.properties (run zookeeper)
 2. ./bin/kafka-server-start  ./etc/kafka/server.properties

## To Start the mongo Source Connector
1. Start MongoDB
2. ./bin/connect-standalone ./etc/kafka/connect-standalone.properties ./etc/mongotry.properties

## To Start Redis Sink Connector
1. Start Redis
2. ./bin/connect-standalone ./etc/kafka/connect-standalone-2.properties ./etc/redis-sink.properties

## To Start the pipeline (from mongo to redis)
1.  Start Mongo and Redis
2.  ./bin/connect-standalone ./etc/kafka/connect-standalone.properties ./etc/mongo.properties ./etc/redis-sink.properties

## To Start Console Producer/Consumer
1. ./bin/kafka-json-schema-console-producer \
--broker-list localhost:9092 --topic topicName \
--property value.schema='{"type”:”object”}’ \
--property parse.key=true \
--property key.schema='{"type":"string"}'
2. ./bin/kafka-json-schema-console-consumer \
--bootstrap-server localhost:9092 \
--topic toko \
--from-beginning \
--property value.schema='{"type”:”object”}’ \
--property parse.key=true \
--property key.schema='{"type":"string"}'

