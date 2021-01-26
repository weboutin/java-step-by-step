首先进入到 MyBatis 的[官网](https://mybatis.org/mybatis-3/getting-started.html)，通过 maven 下载 MyBatis;

MyBatis 的 [github repo](https://github.com/mybatis/mybatis-3/tree/master/src/site)


官网首先推荐的方式是使用 XML 来管理数据库连接信息和 Mapper 信息，同时也支持了不实用 XML 的方式来管理这些信息；

    String resource = "org/mybatis/example/mybatis-config.xml";
  
看文档第一个困惑点是 xml 文件路径是如何管理的？

session 生命周期

1. 数据库连接中文编码
2. 开发者模式输出sql语句
3. xml 和 annotation 的实现\
    parameterType
    resultType
4. 获取insert/update 的insertid
5. transaction autoCommit
