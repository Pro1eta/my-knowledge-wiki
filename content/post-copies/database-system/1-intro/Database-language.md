---
title: 数据库语言
aliases:
  - DML
  - DDL
  - query
  - query language
  - data dictionary
  - metadata
---
数据库系统提供**数据定义语言**（Data-Definition Language，**DDL** ）来定义数据库模式，
并提供**数据操纵语言**（Data-Manipulation Language，**DML** ）来表达数据库的查询和更新。
# 数据定义语言（DDL）

数据库中的数据值必须满足某些[一致性约束（consistency constraints）](data-model.md)。DDL 语言提供了指明这样的约束的工具。

- 域约束（domain constraint）。每个属性都必须对应于一个所有可能的取值构成的域，域约束是完整性约束的最基本形式。
- 引用完整性（referential integrity）。规定一个关系中给定属性集上的取值也在另一关系的某一属性集的取值中出现。
- 授权（authorization）。对用户加以区别，例如只能**读**不能**插入**，只能**读**和**插入**而不允许**删除**等。

和其他程序设计语言一样，DDL 的语句将产生输出。输出放在 **数据字典（data dictionary）** 中，数据字典包含 **元数据（metadata）** ，元数据是关于数据的数据。

可以把数据字典看作一种特殊的表，这种表只能由数据库系统本身（不是常规的用户）来访问和修改。

我们举一个例子进行说明：

```sql
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    HireDate DATE,
    DepartmentID INT
);
```

`CREAT TABLE` 语句不返回如同  `SELECT` 语句那样的结果集，而是在后台生成关于 `Employees` 表的 元数据。这些**元数据**组成了**数据字典**，可以看作一个新的表。

如前面所说，元数据是关于数据的数据，给出了`Employees` 表 的描述性信息，下面给一些例子：

- 表名： `Employees`
- 列名和数据类型：
    - `EmployeeID`：整数 (`INT`)
    - `FirstName`：变长字符串，最大长度 50 (`VARCHAR(50)`)
    - `LastName`：变长字符串，最大长度 50 (`VARCHAR(50)`)
    - `HireDate`：日期 (`DATE`)
    - `DepartmentID`：整数 (`INT`)
- 约束信息：
    - `EmployeeID` 是主键 (`PRIMARY KEY`)
    - `FirstName` 和 `LastName` 是非空 (`NOT NULL`)
- 表的所有者
- 表的创建时间
- 等等其它信息...
# 数据操作语言（DML）

DML 使用户能访问或者操纵数据。基本的访问类型有**增删查改**，即
- 对存储在数据库中的信息进行检索；
- 向数据库中插入新的信息；
- 从数据库中删除信息；
- 修改数据库中存储的信息。

DML 大致分成以下两类：

- **过程化**的（procedural DML）- 要求用户指定需要什么数据以及如何获得这些数据。
- **声名式**的（declarative DML or nonprocedural DML）- 用户指定需要什么数据，不必指明如何获得这些数据。

**查询（query）** 语句对信息进行检索。DML 中信息检索的部分称为查询语言（query language）。

>[!NOTE]
> 实践中，一般将查询语言（query language）和数据操作语言（DML）混用。

