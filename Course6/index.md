CQRS
====

Command query responsibility segregation

## Command

CUD

## Query

R

1. API composition
2. Dedicated data view


OrderHistoryService

handler  -> order.created
         -> customer.updated
         -> ...

ElasticSearch


### Issues

1. Handle duplicated messages
    1.1 
        PROCESSED_EVENT table
        eventId
        maxEventId
    1.2 
        幂等性

## API Gateway

1. API composition
2. Edge function(Authentication, Authorization, Rate limit, Monitor)
3. Proxy