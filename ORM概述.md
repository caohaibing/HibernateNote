####ORM概述
#####什么是JDBC
JDBC代表Java Database Connectivity，提供了一些列API供Java程序访问关系型数据库。这些Java API允许Java程序运行SQL语句。
JDBC的优点：
- **简洁和简单的SQL操作**
- **性能好**
- **适合于小应用**
- **语法简单，易于使用**

JDBC的不足：
- **在大型项目中会很复杂**
- **大量重复代码**
- **没有封装**
- **不利于实现MVC模型**
- **插叙特定于某个数据库**

#####为什么需要ORM
当我们开发一个面向对象的系统时，在对象模型和关系型数据库之间存在不匹配的情况。
- **关系型数据库中不存在集成的概念，而这在卖面向对象的程序中很正常**
- **关系型数据库中靠主键来确定一条记录，而在Java中存在==和equals()**
- **在Java中通过来表示关联，而在关系型数据库中靠外键表示关联**
- **二者访问对象的方式存在差异**

#####什么是ORM
ORM是一种在关系型数据库和面向对象的语言之间转换数据的编程技术。与JDBC相比，ORM系统有以下优点：
- **让业务代码访问对象，而不是数据库表**
- **隐藏了SQL查询的细节**
- **基于JDBC**
- **封装了不同数据库之间的差异**
- **实体基于逻辑概念而不是数据库结构**
- **事务管理和自动生成键**
- **快速开发**

一个ORM解决方案包括下面四个方面：
- **执行基本CRUD的API**
- **支持查询的语言或API**
- **配置映射元数据**
- **优化配置**

#####常见ORM框架
- **Enterprise JavaBeans Entity Beans**
- **Java Data Objects**
- **Castor**
- **TopLink**
- **Spring DAO**
- **Hibernate**
- ...

