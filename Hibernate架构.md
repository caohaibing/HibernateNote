####Hibernate架构
![Hibernate_high_level](http://www.tutorialspoint.com/images/hibernate_high_level.jpg)

![Hibernate_arch](http://www.tutorialspoint.com/images/hibernate_architecture.jpg)

#####Configuration对象
Configuration对象是在任何Hibernate程序中第一个被创建的Hibernate对象，通常在程序初始化时创建一次。它代表了Hibernate需要的配置或属性文件。Configuration对象提供了两个主要的组件：
- **数据库连接：**<code>hibernate.properties</code>、<code>hibernate.cfg.xml</code>
- **类映射**

#####SessionFactory对象
Configuration对象可以创建一个SessionFactory对象，用来根据已经提供的配置文件为系统配置Hibernate和实例化一个Session对象。SessionFactory是线程的安全的可以被系统中的所有线程使用。
SessionFactory是一个重量级对象，所以，通常我们在系统启动时创建一个SessionFactory对象，以备后续使用。每个数据库需要一个SessionFactory对象。所以，如果你使用多个数据就必须创建多个SessionFactory对象。

#####Session对象
Session用来获取一个数据库物理连接。Session对象是轻量级的，每次和数据库进行交互时都会实例化它。
Session对象不可持续打开太长时间，因为它通常不是线程安全的，我们在需要时进行创建和销毁。

#####Transaction对象
一个Transaction代表了数据库中一个工作单元，绝大部分数据库都支持事务功能。
这是一个可选对象，我们可以不适用这个接口，而在自己在代码中实现事务管理。

#####Query对象
查询

#####Criteria对象
Criteria对象用于创于创建和执行面向对象的标准查询来取出对象。