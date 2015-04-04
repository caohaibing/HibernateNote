####Hibernate性能调优
#####优化
>优化是困难的

- **性能瓶颈在哪？**
	- **框架还是你？**
	- **何时优化？**

- **随时保持正确性**
	- **单元测试，还不够。**
	- **自动集成测试。**

>过度优化是一切罪恶的根源

#####优化原则

- **确保稳定的生产环境**
- **量化时间和空间**
	- **时间：在每一层进行分离定时**
	- **空间：加大堆空间->更长的GC时间->系统更慢**
- **量化数据库**
	- **IO分析**
	- **查询计划**
- **更多的量化指标 -> 自动化**

- **在DAO/Session.query()进行性能监控**
- **关注Java虚拟机堆的大小**
- **开启Hibernate JMX**
- `<property name="hibernate_generatestatistics">
			true
	</property>`
- **数据库监控工具**

#####分析Hibernate
- **输出SQL语句**
- `<property name="show_sql"> true </property>`
- `<property name="format_sql"> true </property>`
- **Log4J配置**
- `org.hibernate.SQL -> DEBUG`
- `org.hibernate.type -> TRACE`
- **在JDBC连接上使用P6Spy或者Log4JDBC**

#####延迟加载
![Lazy_loading](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-16-728.jpg?cb=1337545617)

- **LazyInitializationException**
- **N + 1查询问题**
	- **查询N个用户列表**
	- `HQL：SELECT u FROM User`

![Hibernate_loading](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-19-728.jpg?cb=1337545617)

![Hibernate_loading](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-20-728.jpg?cb=1337545617)

![Hibernate_loading](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-21-728.jpg?cb=1337545617)

![Hibernate_loading](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-22-728.jpg?cb=1337545617)

#####搜索查询

![Seach query](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-24-728.jpg?cb=1337545617)

![Search queries](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-26-728.jpg?cb=1337545617)

![Search queries](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-27-728.jpg?cb=1337545617)

![Search queries](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-28-728.jpg?cb=1337545617)

![Search queries](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-29-728.jpg?cb=1337545617)

#####大集合

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-31-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-32-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-33-728.jpg?cb=1337545617)

![large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-34-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-35-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-36-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-37-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-38-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-39-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-40-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-41-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-42-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-43-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-44-728.jpg?cb=1337545617)

![Large Collection](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-45-728.jpg?cb=1337545617)

![Dirty data](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-47-728.jpg?cb=1337545617)

![Dirty data](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-48-728.jpg?cb=1337545617)

![Query hints](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-49-728.jpg?cb=1337545617)

![Query hints](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-50-728.jpg?cb=1337545617)

![Large Update](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-51-728.jpg?cb=1337545617)

![Large Update](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-52-728.jpg?cb=1337545617)

![Cherish your database](http://image.slidesharecdn.com/20120519jeeconfhibernateperformancetuning-120520132453-phpapp02/95/hibernate-performance-tuning-jeeconf-2012-53-728.jpg?cb=1337545617)