
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
    

