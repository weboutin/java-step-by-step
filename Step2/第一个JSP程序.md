## Tomcat

通过 Apache 官网可以直接[下载 Tomcat](https://tomcat.apache.org/download-90.cgi)，目前 tomcat 10 还是 beta 版本，这里使用 tomcat 9。

Tomcat 是一个开箱即用的服务器，进入 Tomcat 的目录(下面通过  ~Tomcat 来表示 Tomcat 的目录)，通过 ./bin/startup.sh 和 ./bin/shutdown.sh 可以 启动/停止服务器。

启动完成后，浏览器访问 127.0.0.1:8080 即可访问。

## 第一行 Java Web 程序

根据 Tomcat 的默认配置文件，服务器默认绑定的端口是 8080，默认项目所在路径是 ~Tomcat/webapps/ROOT。

删除 ~Tomcat/webapps/ROOT 下的所有文件，创建属于自己的 index.jsp :

    <% out.println("<h1>Helloworld</h1>");%>
  
删除 ROOT 下所有文件然后在这编写自己的项目在生产上并不是一个很好的做法，但这是最快的方法，部署项目不是这里学习的重点，故不拘泥于做法是否合适；

out 是 JSP 的内置对象，可以在程序中直接使用。

.jsp 文件会被编译成 .java 和 .class 文件，保存在 ~tomcat/work/Catalina/localhost/ROOT/org/apache/jsp/ 目录下

在 Tomcat 默认为开发模式，在这个配置下，修改 .jsp 文件，可以在不重启 Tomcat 的情况下，重新编译成 .java 和 .class 文件，换言之，修改 jsp 文件，直接刷新浏览器即可看到变更效果。
