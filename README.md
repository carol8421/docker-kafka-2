# loicmathieu/kafka
Docker kafka container. It uses supervisord to launch both Kafka and Zookeper so no need to launch a separate Zookeeper instance.

It exposes tow ports :
- 2181 : zookeeper port
- 9092 : kafka port

To launch it, you need to specify two environemt variables : 
- ADVERTISED_HOST : kafka host
- ADVERTISED_PORT : kafka port

For exemple : 
```
docker pull loicmathieu/kafka
docker run -p 2181:2181 -p 9092:9092 --env ADVERTISED_HOST=localhost --env ADVERTISED_PORT=9092 -d loicmathieu/kafka
```