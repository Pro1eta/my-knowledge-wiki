---
title: 数据模型
aliases:
  - model
  - integrity constraints
  - data model
  - Relational model
  - Entity-Relationship model
  - consistency constraints
---
**数据模型（Data models）**：对[数据抽象](data-abstraction.md)的描述方法。

具体来说，如果有一系列工具，描述了：

- 数据
- 数据关系
- 数据语义（data semantics）
- 一致性约束（consistency constraints）

那么这一系列工具的集合就定义为**数据模型**。数据模型可以认为是框架和数据组织的范式。

数据语义是数据的真实含义，数据约束是实现数据语义的强制条件。

例如 Age 的语义是“一个人的年龄，通常以年为单位，且必须是一个正整数”，而约束是“Age>0”。

**数据语义**（data semantics）和**一致性约束**（consistency constraints）合称为完整性约束（integrity constraints）。

>[!NOTE] 其它定义方式
>**数据模型**也可定义为：数据的**语法定义** + 数据的**语义定义** + **数据操作**。
>
>语法定义：数据项、数据间的关系。
>
>语义定义：完整性约束。
>
>数据操作（仅在一些模型中有，比如关系数据模型）。

# 分类

## 关系模型（Relational model）

简单来说，就是用表格来表示数据和其间的关系。例如二维表结构。

## 实体-联系模型（Entity-Relationship model）

使用**实体**（entity）和**联系**（relationship）来对**对象**和其之间的关联建模，例如ER图。

---

其它还有面向对象模型、半结构化数据模型、XML等。

# 模型，模式和实例的关系

根据数据模型、[数据模式](instances-schemas.md)和[数据模式的实例](instances-schemas.md)的定义，我们以关系模型为例进行说明：

> [!example] 
> - 关系数据模型（Relational data model）：$R = {<a_1, a_2, \cdots, a_n>}$。
> - 关系数据模式（Relational data schema）：$\text{customer} = <\text{c\_name},\text{c\_id},\text{street},\text{city}>$。
> - 关系模式实例（instance of schema）：$<\text{Kobe\_Bryant},\text{24},\text{street\_101},\text{Los\_Angeles}>$。
 
关系数据模型描述了一般的数据组织方法。关系数据模式描述了具体语境中，一个“顾客信息表”的每一行是怎样的。而关系数据实例描述了实际的一行。

>[!NOTE]
>一个类比是：data model - 一种类型，data schema - 该类型的一个变量，instance - 为该变量所赋的值。

