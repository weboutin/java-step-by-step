## 环境配置

[Java.com](https://www.java.com/zh-CN/download/) 下载安装完成后，保证控制台可以执行 java, javac 和 jar.
java javac jar 三者的关系是什么？简单来说，开发的时候编写的文件是  .java 文件，使用 javac 命令 可以将 .java 文件编译成，.class 文件，使用 java 命令可以执行 .class 文件；jar 命令可以将 单个或多个 .class 文件打包成 .jar 文件，在 java 程序里面可以引用 .class 文件或者 .jar 文件。

## 编译执行 Helloworld

创建 App.java 文件

    public class App {
        public static void main(String[] args){
            System.out.println("Hello World!");
        }
    }

编译：

javac App.java

执行：

java App

输出：

Hello World!

接下来我们通过解答以下几个问题来挖掘这个程序；

为什么类名和文件名要保持一致？

为什么使用public关键字

为什么使用static关键字

为什么返回类型是 void

为什么接收参数是 String[] args

为什么没有import任何包就能使用 System 类？
