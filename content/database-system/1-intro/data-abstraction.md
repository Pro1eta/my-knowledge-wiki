---
title: 数据抽象
aliases:
---
数据抽象是对数据的描述。对数据进行应用的时候，可以从不同的三层来描述数据：
- 视图层（**View level**）：不同用户根据其使用而对数据的描述。
- 逻辑层（**Logical level**）：描述数据项如何存储在 [DBS](DB-DBMS-DBS-DBAS.md) 中，以及数据间的关系。
- 物理层（**Physical level**）：描述数据在文件和外存中是具体怎么存储的。

> [!NOTE]
> 一般来说，数据的抽象层和[模式（schema）](instances-schemas.md)是一个意思。例如 View Level 这个词和外模式（external schema）互换，这是没什么问题的。
