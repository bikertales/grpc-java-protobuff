# publisher
Publisher API to a Kafka or any broker

For Kafka

set KAFKA_HEAP_OPTS="-Xmx1G -Xms1G" 

./zookeeper-server-stop.sh config/zookeeper.properties & 

./kafka-server-start.sh config/server.properties &  

./kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic policyissued 

./kafka-topics.bat --describe --zookeeper localhost:2181 --topic policyissued 

./kafka-console-producer.bat --broker-list localhost:9092 --timeout=100000 --topic policyissued 

./kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic policyissued --from-beginning 

.\build\install\publisher\bin\publisher-server.bat

.\build\install\publisher\bin\publisher-client.bat my-message

