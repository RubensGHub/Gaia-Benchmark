# Gaia-Benchmark

Projet de fin de module d'Architecture Microservices

[...]


## Notes des commandes terminales : 

- Bases :
```
docker compose up --build
```
```
docker compose up -d
```
```
docker compose down
```

- Remove all stopped containers :
```
docker container prune
```
- Remove all stopped volumes :
```
docker volume prune
```

- Liste des clusters :
```
docker compose ps
``` 

### Volumes : 
```
docker volume ls
```
```
docker compose down -v
```
```
docker volume rm <nom volume>
```

### Networks :
```
docker network ls
```
```
docker network create <nom_network>
```

### Logs:
```
docker logs <nom_service>
```

### Kafka :
```
docker exec -it kafka_broker bash
```
```
kafka-topics.sh --bootstrap-server kafka:9092 --list
```

- Get les events :
```
kafka-console-consumer.sh --bootstrap-server kafka:9092 --topic 
```
```
order-created --from-beginning
```
### Kafka topics : 

- Liste les topics : 
```
docker exec -it kafka_broker /opt/kafka/bin/kafka-topics.sh \
  --bootstrap-server kafka:9092 \
  --list
```

- Add un topic : 
```
docker exec -it kafka_broker /opt/kafka/bin/kafka-topics.sh \                                                                            
  --bootstrap-server kafka:9092 \
  --create \
  --topic <nom du topic, ex: inventory.updated> \
  --partitions 1 \
  --replication-factor 1
```


### POSTGRE :
- Lancer le command-line interface de postgre avec telle bdd (pour vérifier quelle marche bien) :
```
docker exec -it order_db_postgres psql -U <nom $POSTGRES_USER> -d my_db
```
```
docker exec -it order_db_postgres psql -U db_user -d my_db
```

- Montre les tables existantes : ```\dt```







