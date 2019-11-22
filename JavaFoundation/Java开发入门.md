#一 Java开发入门第一章
## 1. Java概述
### 1.1 JavaSE、JavaEE和JavaME
java分为三个技术平台：JavaSE、JavaEE和JavaME<br>
* <i><b>Java SE（Java Platform Standard Edition）标准版，是为开发普通桌面和商务应用程序提供的解决方案。</b></i>JavaSE是三个平台中最核心的部分，JavaEE和JavaME都是从JavaSE的基础上发展而来的，JavaSE平台中包括了Java最核心的类库，如集合、IO、数据库连接以及网络编程等。<br>
* <i><b>Java EE(Java Platform Enterprise Edition) 企业版，是为开发企业级应用程序提供的解决方案。</b></i>JavaEE可以被看作一个技术平台，该平台用于开发、装配以及部署企业级应用程序，其中主要包括Servlet、JSP 、JavaBean 、JDBC、EJB、Web Service等技术。<br>
* <i><b>Java ME(Java Platform Micro Edition) 小型版，是为开发电子消费产品和嵌入式设备提供的解决方案。</b></i>JavaME主要用于小型数字电子设备上软件程序的开发。例如，为家用电器增加智能化控制和联网功能，为手机增加新的游戏和通讯录管理功能。此外，Java ME提供了HTTP等高级Internet协议，使移动电话能以Client/Server方式直接访问Internet的全部信息，提供最高效率的无线交流。<br>
### 1.2 Java跨平台性
通过Java语言编写的应用程序在不同的系统平台上都可以运行。
只要在需要运行java应用程序的操作系统上，先安装一个Java虚拟机(JVM Java Virtual Machine)即可。由JVM来负责Java程序在该系统中的运行。
### 1.3 Java运行机制
Java程序运行时，必须经过编译和运行两个步骤。首先将后缀名为.java的源文件进行编译，最终生成后缀名为.class的字节码文件。然后Java虚拟机将字节码文件进行解释执行，并将结果显示出来。<br>
以HelloWorld为例，对Java程序的运行过程进行详细的分析，具体步骤如下：
* 编写一个HelloWorld.java的文件。<br>
* 使用“javac HelloWorld.java”命令开启Java编译器并进行编译。编译结束后，会自动生成一个HelloWorld.class的字节码文件。<br>
* 使用“java HelloWorld”命令启动Java虚拟机运行程序，Java虚拟机首先将编译好的字节码文件加载到内存，这个过程被称为类加载，它是由类加载器完成的，然后虚拟机针对加载到内存中的Java类进行解释执行，便可看到运行结果。<br>
### 1.4 包的定义与使用
包用来存放类，相同功能的类存放于同一包中。在程序第一行声明包，声明实例如下：<br>
<pre>package cn.itcast.chapter01; //<i>使用package关键字声明包</i>
public class Example01{…}</pre>
当调用另一个包中的类时，使用import，调用实例如下：<br>
<pre>import 包名.类名//<i>调用某个类</i>
import 包名.*//<i>调用此包中所有类</i></pre>
## 2. JDK、JRE、JVM
### 2.1 JVM -- java virtual machine
JVM即java虚拟机，java程序被编译为.class文件后，这种.class文件可以在虚拟机上执行，虚拟机充当.class文件与操作系统交互的桥梁。<br>
JVM与实际机器一样，有自己的指令集、运行时的内存区域。其通过抽象操作系统和CPU，提供与平台无关的代码执行方法。<br>
JVM主要工作为解释自己的指令集到CPU的指令集，或OS的系统调用，对上层.java文件不关心，只关注.class文件。.class由JVM指令集、符号表、一些补助信息组成。
![](https://alleniverson.gitbooks.io/java-basic-introduction/content/%E7%AC%AC1%E7%AB%A0%20Java%E5%BC%80%E5%8F%91%E5%85%A5%E9%97%A8/img/jvm1.png) <br>
![](https://alleniverson.gitbooks.io/java-basic-introduction/content/%E7%AC%AC1%E7%AB%A0%20Java%E5%BC%80%E5%8F%91%E5%85%A5%E9%97%A8/img/jvm3.png) <br>
### 2.2 JRE -- java runtime environment
JRE指java运行环境，运行.class文件只有JVM不够，还需要有JRE，JRE由两部分组成，一部分为JVM，进行与虚拟机的交互，一部分为lib，保存JVM所需要的类库。<i><b>`jvm+lib=jre`</i></b><br>
JRE与具体的CPU及操作系统有关，不同操作系统所需JRE版本不同。
### 2.3 JDK -- java development kit
JDK是java开发工具包，其包含：bin、conf、include、jmods、legal、lib六个文件夹和一些其他文件。在java运行时bin、include、lib、 jre起作用。因此JDK包含JRE，JRE包含JVM。
* bin:最主要的是编译器(javac.exe)
* include:java和JVM交互用的头文件
* lib:类库
* jre:java运行环境
### 2.4 三者联系
我们利用JDK（调用JAVA API）开发了属于我们自己的JAVA程序后，通过JDK中的编译程序（javac）将我们的文本java文件编译成JAVA字节码，在JRE上运行这些JAVA字节码，JVM解析这些字节码，映射到CPU指令集或OS的系统调用。
