JSON 几乎成为 WEB 前后端通讯的标准格式（有些仍然使用 XML，但 JSON 应用才是最广泛的）

但是 JSON 并不是 Java 原始支持的数据格式，需要做些处理，才能让是 Servlet 返回 JSON 数据；

## 最简单的实现方式

修改 response 的 ContentType 为 test/json，并且输出的时候为JSON格式的字符串，那么浏览器就会将结果识别为 JSON 对象；

    response.setContentType("application/json;charset=UTF-8");
    PrintWriter out = response.getWriter();
    out.println("{\"hello\":\"world\"}");

但是对于复杂的对象而言，拼接 JSON 格式的字符串并不是一个轻松的事情，考虑在 Java 编码中使用 key/value 的数据格式，然后返回的时候转换为 JSON 字符串接即可。

去 [Maven 仓库](https://mvnrepository.com/) 搜索 JSON， 看看都有些什么优秀的第三方库可以支持这种做法；

可以看到 [JSON in Java](https://mvnrepository.com/artifact/org.json/json) 这个库用的人最多，考虑看看这个库用起来是否顺手；

通过 [Maven Search](https://search.maven.org/artifact/org.json/json) 可以搜索到这个库的 JAR 包下载方式

Maven Search 的搜索语法是： ${groupId}:${artifactId} ，那么搜索上面json库的语法就是: org.json:json；也支持g:org.json AND a:json 这种写法。

更多关于 Maven 的知识，会在下一篇文章[《认识Maven》](https://github.com/weboutin/javaweb-step-by-step/tree/main/Step3)展开；

通过 [Github 的文档](https://github.com/stleary/JSON-java)，可以了解到 JSON in Java 的用法。

根据我们的需求文档，我们希望返回的通用 JSON 格式是这样的：

    {
        code: 0,
        msg: "获取成功",
        data: {}
    }
    
那么，使用 JSON-java 的实现便是：
 
    response.setContentType("application/json;charset=UTF-8");
    JSONObject output = new JSONObject();
    JSONObject data = new JSONObject();
    output.put("code", 0);
    output.put("msg", "获取成功");
    output.put("data", data);
    PrintWriter out = response.getWriter();
    out.println(output);


