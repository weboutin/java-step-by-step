## JDBC 

我们常说的 JDBC 一般是指 Java Database Connectivity API，即由  java.sql 或者 javax.sql 包提供的一套数据库操作接口。

Oracle / DB2 / MYSQL 等关系型数据库官方都提供有对应的 jar 包来实现 JDBC API。

因为有这套接口定义，Java 可以通过改动很少的代码就实现不同数据库之间的切换，下面以 MySQL 连接为例进行展开。


## JDBC - MySQL

通过 [MySQL的官网](https://dev.mysql.com/downloads/connector/j/) 可以下载对应的 jar 包。

下面通过可以通过 [MySQL官网](https://dev.mysql.com/doc/connector-j/8.0/en/connector-j-examples.html)的例子来学习使用 JDBC 。

通过完整[源代码](https://github.com/weboutin/sbs-impl/tree/release/v1.0) 运行可以直接看到效果，下面进行一步步的拆解：

    class App {
        public static void main(String[] args) {
            try {
                Class.forName("com.mysql.cj.jdbc.Driver");
                conn = DriverManager.getConnection("jdbc:mysql://localhost/test?user=root&password=root");
            } catch (Exception e) {
                System.out.println(e.getMessage());
            }
        }
    }
  


[MySQL JDBC Driver](https://github.com/mysql/mysql-connector-j/blob/release/8.0/src/main/user-impl/java/com/mysql/cj/jdbc/Driver.java)

Statement 的用处是什么？为什么需要close？

ResultSet 的用处是什么？为什么需要close？
