# E-commerce con arquitectura hexagonal y DDD

Versión 2 del [e-commerce con CQRS y Kafka](https://github.com/AdtC818/ARQUITECTURA-CQRS-Y-EDA-EN-SPRINGBOOT-CON-APACHE-KAFKA): pasamos los microservicios de MVC a arquitectura hexagonal con Domain-Driven Design. Cada servicio separa dominio, aplicación (casos de uso y puertos) e infraestructura (adaptadores: REST, JPA y Kafka).

## Servicios
| Servicio | Puerto |
|---|---|
| orderservice | 8082 |
| shippingservice | 8083 |
| paymentservice | 8084 |
| inventoryservice | 8085 |
| edakafka | 8080 |
| gateway | 8081 |
| Kafka / MySQL | 29092 / 3306 |

## Cómo correrlo

    docker compose up --build

## Mi aporte (Angel Torres)
- Refactoricé orderservice a DDD: agregado Order, objetos de valor OrderId y OrderStatus, evento OrderCreatedEvent, casos de uso y bus de eventos con Kafka.
- Pasé paymentservice a puertos y casos de uso, y configuré el gateway.