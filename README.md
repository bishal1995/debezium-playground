### Reference Play ground for Debezium  along with kafka 


#### Reference : https://debezium.io/documentation/reference/1.2/configuration/avro.html

##### Run AVRO console consumer

```$xslt
$ docker run -it --rm --name avro-consumer \
    debezium/connect:1.2 \
    /kafka/bin/kafka-console-consumer.sh \
      --bootstrap-server kafka:9092 \
      --property print.key=true \
      --formatter io.confluent.kafka.formatter.AvroMessageFormatter \
      --property schema.registry.url=http://schema-registry:8081 \
      --topic db.myschema.mytable
```