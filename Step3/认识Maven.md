
## Maven

有点类似于 Node.js 的 NPM 和 PHP 的 composer，业内选择了 Maven 来管理 Java 的 jar 包；通过 Maven 可以快速初始化工程项目，通过 Maven 可以高效地管理项目的 jar 包；

继续我们的课程，我们的项目到了现在，已经有了 servlet-api.jar 和 json-20201115.jar 两个 jar 包的依赖，随着项目的开发，会加入越来越多的 jar 包。

目前我们采取的管理办法是找到 jar 包对应的官方网站，然后下载下来放到目录的 WEB-INF/lib/ 下，这种做法非常低效，完全可以通过 Maven 的 nvm install 命令的直接下载 jar 包。

首先，我们使用 mvn 来初始化我们的项目，使得我们的项目可以由 mvn 来管理依赖。

## 使用 Maven 初始化工程目录

查阅 [Maven 官方文档](http://maven.apache.org/guides/getting-started/index.html) 可知，使用以下命令可以初始化工程项目：

    mvn archetype:generate \
    -DarchetypeGroupId=org.apache.maven.archetypes \
    -DarchetypeArtifactId=maven-archetype-webapp \
    -DgroupId=com.mycompany.app \
    -DartifactId=my-webapp \
    -DarchetypeCatalog=internal 
  

之前的项目结构：

* WEB-INF   
	* |- classes
		* |- Users.class
    * |- lib
        * |- json-20201115.jar
        * |- servlet-api.jar
    * |- web.xml
* Users.java

使用 Maven 后的项目结构

* src
    * |- main
        * |- resources
        * |- webapp
            * |- index.jsp
            * |- WEB-INF
                * |- web.xml
* pom.xml

先来分析以下这个工程目录：

pom.xml 文件是 Maven 的配置文件，项目依赖的 jar 包都在这里描述，类似于 Node.js 的 package.json 和 PHP 的 composer.json

src/main 里包含项目的所有编码

src/main/resources 里面存储项目用的静态文件，html/js ... 等

src/main/webapp 里面的的是 tomcat 访问的文件，跟之前的项目结构类似。

项目结构经过了这么一次调整，项目就不能之前放到 tomcat 的 webapps 里面直接使用了，而需要使用 maven 先进行打包。

在项目目录下执行 

    mvn package -f ./pom.xml
    
在 src 下会生成 target 目录，里面包含了编译后的 .class 文件。

第一次打包需要下载很多 maven 依赖的，打包速度较慢。




