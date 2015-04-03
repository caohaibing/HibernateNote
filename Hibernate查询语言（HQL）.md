####Hibernate查询语言（HQL）
#####FROM子句

    String sql= "FROM Employee";
    Query query = session.createQuery(hql);
    List results = query.list();
#####AS子句
为类其别名

    String hql = "FROM　Employee AS E";
    Query query = session.createQuery(hql);
    List results = query.list();

#####SELECT子句
查询

    String hql = "SELECT E.firstName FROM Employee AS E";
    Query query = session.createQuery();
    List results = query.list();

#####WHERE子句
指定查询条件

    String hql = "FROM Employee E WHERE E.id = 10";
    Query query = session.createQuery(hql);
    List results = query.list();

#####ORDER BY子句
对查询出的结果进行排序

    String hql = "FROM Employee E WHERE E.id > 10 ORDER BY E.salary DESC";
    Query query = session.createQuery(hql);
    List results = query.list();

#####GROUP BY子句
分组

    String hql = "SELECT SUM(E.salary) , E.firstName FROM Employee E GROUP BY E.firstName";
    Query query = session.createQuery(hql);
    List results = query.list();

#####使用命名参数
Hibernate支持在它的HQL查询中使用命名查询。避免SQL注入。

    String hql = "FROM Employee E WHERE E.id = :employee_id";
    Query query = session.createQuery(hql);
    query.setParameter("employee_id", 10);
    List results = query.list();

#####UPDATE子句
支持批量更新。

    String hql = "UPDATE Employee set salary  = :salary WHERE id = :employee_id";
    Query query = session.createQuery(hql);
    query.setParameter("salary", 1000);
    query.setParameter("employee_id", 10);
    int result = query.executeUpdate();
    System.out.println("Rows affected: " + result);

#####DELETE子句

    String hql = "DELETE FROM Employee WHERE id = :employee_id";
    Query query = session.createQuery(hql);
    query.setParameter("employee_id", 10);
    int result = query.executeUpdate();
    System.out.println("Rows affected: " + result);

#####INSERT子句

    String hql = "INSERT INTO Employee(firstName, lastName, salary) SELECT firstName, lastName, salary FROM old_employee";
    Query query = session.createQuery();
    int result = query.executeQuery();
    System.out.println("Rows affected: " + result);

#####聚合方法
-  **avg**
-  **count**
-  **max**
-  **min**
-  **sum**

#####分页

    Query setFirstResult(int startPosition);
    Query setMaxResults(int maxResult);

