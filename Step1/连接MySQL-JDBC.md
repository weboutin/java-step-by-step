## JDBC 

我们常说的 JDBC 一般是指 Java Database Connectivity API，即由  java.sql 或者 javax.sql 包提供的一套数据库操作接口。

Oracle / DB2 / MYSQL 等关系型数据库官方都提供有对应的 jar 包来实现 JDBC API。

因为有这套接口定义，Java 可以通过改动很少的代码就实现不同数据库之间的切换，下面以 MySQL 连接为例进行展开。


## JDBC - MySQL

通过 [MySQL的官网](https://dev.mysql.com/downloads/connector/j/) 可以下载对应的 jar 包。

下面通过可以通过 [MySQL官网](https://dev.mysql.com/doc/connector-j/8.0/en/connector-j-examples.html)的例子来学习使用 JDBC 。

首先建立 App.java

  

[MySQL JDBC Driver](https://github.com/mysql/mysql-connector-j/blob/release/8.0/src/main/user-impl/java/com/mysql/cj/jdbc/Driver.java)
