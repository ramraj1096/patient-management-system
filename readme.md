# 💊 Patient Management System – Java Microservices

A microservices-based Patient Management System using Spring Boot. Includes services for managing patients, billing, and notifications with Kafka messaging and PostgreSQL persistence.

---

## 🔗 GitHub Repository

```bash
git clone https://github.com/ramraj1096/patient-management-system.git
```

---

## ✨ Features Implemented

- ✅ **Patient Management** – Create, update, and fetch patient records.
- ✅ **Auth service** – User able to register and login.
- ✅ **Billing Service Integration** – gRPC communication for patient billing.
- ✅ **Notification System** – Sends Kafka-driven notifications on key events.
- ✅ **Microservices Architecture** – Loosely coupled services for scalability.
- ✅ **PostgreSQL Integration** – Persistent storage for patient and billing data.
- ✅ **Apache Kafka** – Event-driven communication between services.
- ✅ **Dockerized Setup** – Easy service orchestration via Docker Compose.
- ✅ **Remote Debugging** – Configured with JDWP for seamless debugging.

---

## 🏥 Patient Service

### Environment Variables

```env
JAVA_TOOL_OPTIONS=-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:5005
SPRING_DATASOURCE_PASSWORD=password
SPRING_DATASOURCE_URL=jdbc:postgresql://patient-service-db:5432/db
SPRING_DATASOURCE_USERNAME=admin_user
SPRING_JPA_HIBERNATE_DDL_AUTO=update
SPRING_KAFKA_BOOTSTRAP_SERVERS=kafka:9092
SPRING_SQL_INIT_MODE=always
```

### Full Configuration with Billing Integration

```bash
BILLING_SERVICE_ADDRESS=billing-service
BILLING_SERVICE_GRPC_PORT=9005
JAVA_TOOL_OPTIONS=-agentlib:jdwp\\=transport\\=dt_socket,server\\=y,suspend\\=n,address\\=*:5005
SPRING_DATASOURCE_PASSWORD=password
SPRING_DATASOURCE_URL=jdbc:postgresql://patient-service-db:5432/db
SPRING_DATASOURCE_USERNAME=admin_user
SPRING_JPA_HIBERNATE_DDL_AUTO=update
SPRING_KAFKA_BOOTSTRAP_SERVERS=kafka:9092
SPRING_SQL_INIT_MODE=always
```

---

## 📢 Notification Service

### Environment Variables

```env
SPRING_KAFKA_BOOTSTRAP_SERVERS=kafka:9092
```

---

## 🐳 Kafka Container Configuration

```env
KAFKA_CFG_ADVERTISED_LISTENERS=PLAINTEXT://kafka:9092,EXTERNAL://localhost:9094
KAFKA_CFG_CONTROLLER_LISTENER_NAMES=CONTROLLER
KAFKA_CFG_CONTROLLER_QUORUM_VOTERS=0@kafka:9093
KAFKA_CFG_LISTENER_SECURITY_PROTOCOL_MAP=CONTROLLER:PLAINTEXT,EXTERNAL:PLAINTEXT,PLAINTEXT:PLAINTEXT
KAFKA_CFG_LISTENERS=PLAINTEXT://:9092,CONTROLLER://:9093,EXTERNAL://:9094
KAFKA_CFG_NODE_ID=0
KAFKA_CFG_PROCESS_ROLES=controller,broker
```

---

## 🔄 Kafka Producer Setup (Patient Service)

```properties
spring.kafka.consumer.key-deserializer=org.apache.kafka.common.serialization.StringDeserializer
spring.kafka.consumer.value-deserializer=org.apache.kafka.common.serialization.ByteArrayDeserializer
```

---

## 🛢️ Environment Variables (Database - Auth Service Example)

```env
SPRING_DATASOURCE_PASSWORD=password
SPRING_DATASOURCE_URL=jdbc:postgresql://auth-service-db:5432/db
SPRING_DATASOURCE_USERNAME=admin_user
SPRING_JPA_HIBERNATE_DDL_AUTO=update
SPRING_SQL_INIT_MODE=always
```
