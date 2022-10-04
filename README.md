# kafka-opa-poc
repo for kafka studies with opa for policy management. Initial setup is based on confluent's tutorial: https://developer.confluent.io/quickstart/kafka-docker/

## Installation
1. Run the Docker compose to create Zookeeper, Kafka broker and OPA with 
```
docker-compose up -d
```
2. Create a topic with
```
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
             --create \
             --topic quickstart
```
3. Write messages to a topic with
```
docker exec --interactive --tty broker \
kafka-console-producer --bootstrap-server broker:9092 \
                       --topic quickstart
```
4. Read messages from a topic with
```
docker exec --interactive --tty broker \
kafka-console-consumer --bootstrap-server broker:9092 \
                       --topic quickstart \
                       --from-beginning
```
5. Stop the docker compose
```
docker-compose down
```