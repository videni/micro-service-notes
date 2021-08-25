以Saga的方式管理事务
================

## 1. 为什么需要分布式事务？

## 2. 分布式事务的问题

### 2.1 什么是两阶段提交？

两阶段提交(2PC)，所有的参与者要么全部提交，要么全部回滚。

* NoSQL的数据库不支持2PC
* Message queue 不支持2PC
* 无法保证可用性

### 2.2 CAP理论

## 3. 什么是[Sage模式](http://microservices.io/ patterns/data/saga.html)？

基于异步消息，协调一系列本地事务，以保证数据最终一次性。

### 3.1 如何使用Saga维持数据一致性？

* Pivot transactions

* Compensating transactions

## Saga管理事务的方式？

* 分散
* 中心

## 如何实现“隔离性”？

* 在跨服务，没有数据库事务的情况，我们在微服务系统要面临：

* 更新丢失
* 脏读
* 不可重复读

* 解决方法

* 语义化版本锁(Semantic lock)— 应用层锁
* 可交换更新(Commutative updates)—Design update operations to be executable in any order.
* Pessimistic view — Reorder the steps of a saga to minimize business risk.
* Reread value — Prevent dirty writes by rereading data to verify that it’s unchanged before overwriting it.
* Version file — Record the updates to a record so that they can be reordered.
* By value — Use each request’s business risk to dynamically select the concurrency mechanism.

## 示例