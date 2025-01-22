# Выбор и настройка мониторинга в системе

## Мотивация
Т.к. целевая архитектура представляет из себя - микросервисную архитектуру, то необходимо 
отслеживать процесс непрерывной обработки заказов и состояния сервисов, что достигается благодаря
мониторингу.

## Выбор подхода к мониторингу
- для хранилищ (Postgres, S3) - использовать метод мониторинга USE, т.к. важно увидеть и вовремя отреагировать
на момент, когда хранилищу становится "плохо"
- для сервисов считаю использовать метод "4 golden signals", т.к. он более полным, по сравнению с RED

## Метрики

### S3:
- Bucket Size
- Object Count Metrics
- Request Metrics
- Data Transfer Metrics

### Kafka:
- Network throughput
- Message throughput
- Message in per second
- Consumer group lag
- Cluster info (brokers, status)

### Api services:
- Latency
- Traffic
- Errors
- Saturation

### Base metrics:
- CPU
- RAM
- JVM

## Работа по настройке мониторинга
- т.к. в команде есть девос инженер, он на себя берет настройку и подключение сервисов к prometheus/grafana
- тимлид команды создает необходимые задачи для подключения actuators в API сервисы


# Работа над ошибками

## PostgreSQL
- Current fetch data
- Current insert data
- Current update data
- Active sessions
- Transactions
- Deadlocks
- CPU
- Memory Usage

## Kafka
- CPU - да, необходимо также мониторить, в `Base metrics` - подразумевал, что нужно их отслеживать для всех, как основа

### Api services:
- Latency
- Traffic
- Errors
- Saturation
- Request Rate
- Error rate
- Duration
- Slowest Http methods


### Public API services:
- Kb provided
- Kb transferred (received)
- Latency
- Traffic
- Errors
- Saturation
- Request Rate
- Error rate
- Duration
- Slowest Http methods