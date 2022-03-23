Implementing query
====

在微服务中实现查询


* API组合（API composition）
* 命令查询职责分离（Command query responsibility segregation，CQRS）

## API组合

## 命令查询职责分离

### Command

CUD

### Query

R

2. Dedicated data view

## How to keep data syncronized crossing services

Let's assume OrderHistoryService as a dedicated database-ElasticSearch which needs all data related to order from other services.

OrderHistoryEventHandler subscripes domain events published by MessageQueue
```
    -> order.created
    -> customer.updated
    -> ...
```


### Issues

* Handle duplicated messages
    * 1.1 
    ```
        PROCESSED_EVENT table
        eventId
        maxEventId
    ```
    * 1.2 
        idempotent(幂等性)

## What is API Gateway? 
 
1. API composition
2. Edge function(Authentication, Authorization, Rate limit, Monitor)
3. Proxy