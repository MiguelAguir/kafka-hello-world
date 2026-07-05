# Kafka Hello World

Configuración mínima de **Apache Kafka** en modo **KRaft** (sin Zookeeper) usando **Docker Compose**.

## Descripción

Este repositorio contiene un `docker-compose.yml` que levanta un broker de Kafka en modo **KRaft** (Kafka Raft Metadata mode), eliminando la dependencia de Zookeeper. Ideal para desarrollo local y pruebas rápidas.

## Requisitos

- **Docker** y **Docker Compose**

## Cómo usar

```bash
# Iniciar Kafka
docker compose up -d

# Verificar que está corriendo
docker compose ps

# Producir un mensaje (desde otra terminal)
docker exec -it kafka kafka-console-producer.sh \
  --broker-list localhost:9092 --topic test

# Consumir mensajes
docker exec -it kafka kafka-console-consumer.sh \
  --bootstrap-server localhost:9092 --topic test --from-beginning

# Detener
docker compose down
```

## Configuración

- Puerto: **9092**
- Modo: **KRaft** (sin Zookeeper)
- Persistencia de datos en volumen `kafka_data`
- Cluster ID: `MkU3OEVBNTcwNTJENDM2Qk`

## Tecnologías

- **Apache Kafka** (imagen oficial)
- **Docker Compose**
- **KRaft mode**
