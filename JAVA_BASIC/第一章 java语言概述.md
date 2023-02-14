## 第一章 Java语言概述


1. **基本概念**
  - 数据结构（如何存放数据/载体）+算法（怎么排序/逻辑）=程序
  - 软件：按一定顺序组织的计算机数据与指令的集合   应用程序 and 系统程序
  - 人机交互方式：图形化界面 vs 命令行方式
  - 常用DOS命令：见 java其他常用分区
  - 语言发展：机器语言、汇编语言、高级语言（面向过程&面向对象）
  - 后台开发：Java, PHP, Python, Go, Node.js
  - Green project: Oak    jdk 1.5 -5.0    jdk 8.09.0 10.0(18.3) 11.0(18.9)
  - 应用：Java Web 开发：后台开发   大数据开发   Android应用程序开发：客户端开发
  - Java SE Java EE Java ME Java Card
  - Java两种核心机制：Java虚拟机(Java Virtal Machine)、垃圾收集机制(Garbage Collection)

1. **程序总结**
  - JDK = JRE + JAVA开发工具（javac.exe, java.exe, javadoc.exe...）
  - JRE = JVM + JavaSE核心类库
  - path环境变量：windows执行命令时要搜索的路径
  - 配置path环境变量的原因：为了能在任何文件路径下运行JDK的Java开发工具，当找不到本目录下的该程序时，windows会去系统的环境变量里找路径，然后就能找到path上。必须把该环境变量放在第一位配置。
  - JAVA\_HOME = bin的上一层
  - path = %JAVA\_HOME%\\bin
  - Java源文件以“java”为扩展名。源文件的基本组成部分是类（class）， 如


本例中的HelloWorld类。

- Java应用程序的执行入口是main()方法。它有固定的书写格式：

```
public static void main(String\[\] args) {...}
```

- Java语言严格区分大小写。
- Java方法由一条条语句构成，每个语句以“;”结束。
- 大括号都是成对出现的， 缺一不可。
- 一个源文件中最多只能有一个public类。其它类的个数不限，如果源文件包含

一个public类，则文件名必须按该类名命名。public不能随便给。

- 程序编写-编译-运行过程
  - 编写：.java的源文件储存
  - 编译：javac.exe命令编译java源文件 javac x.java
  - 运行：java.exe命令解释运行我们的字节码文件 java 类名

- 输出语句 System.out.println()；//先输出后换行 ln指的是line
- 输出语句 System.out.print(); //不换行
- 编译过程：编译以后，会生成一个或多个字节码文件，字节码文件的文件名与源文件中的类名相同。得运行有main（）的。
- 块的编写风格：行尾风格（次尾是c语言用的）

```java
public static void main(String[] args) {
...
}
```

- 注释：单行//， 多行/\* \*/，文档/\*\* \*/
- 注释作用：可读性，debug
- 注释特点：单行多行不参与编译；文档的可以被javadoc.exe解析，生成一套以网页文件形式体现的该程序说明文档
- 多行注释不可嵌套
- java API：Application programming interface 语言提供的类库都称为api
- API文档：类库的说明书
- 集成开发环境：
  - Jbuilder
  - NetBeans
  - Eclipse
  - MyEclipse
  - IntelliJ IDEA



