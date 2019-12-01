# Java开发入门第二章
## 1 语法基础
### 1.1 关键字
例如class，public等已经被用，不能作为变量名的字符。</br>
* 特点：关键字中的字母全部小写</br>
### 1.2 标示符
声明变量、方法、类时用于起名的符号。</br>
* 组成：` 英文大小写、数字、$、_ `组成
* 规则：<pre>不能数字开头
不能是关键字
区分大小写</pre>
* 命名规则：<pre><b>包</b>：全部小写  e.g. package cn.itcast.chapter01;// 多级的包，每级都小写
<b>类、接口</b>：每个单词首字母大写  e.g. StudentName
<b>方法、变量</b>：首字母小写，其余单词首字母大写  e.g. studentAge,showAllNames()
<b>常量</b>：全部大写，多个字母用"<b>_</b>"隔开  e.g. PI,STUDENT_MAX_AGE</pre>
### 1.3 注释
* 单行注释： `//注释文字`
* 多行注释： `/* 注释文字 */`
* 文档注释： `/** 注释文字 */`
注释实例：先写注释再写代码<pre>/*
    需求：我准备写一个java程序，把"HelloWorld"这句话输出在控制台

    分析：
        A:要写一个Java程序，必须定义类
        B:把数据能够输出，说明我们的程序是可以独立运行的，而程序要独立运行，必须定义main方法
        C:把数据输出在控制台，必须使用输出语句

    实现：
        A:java语言提供了一个关键字：class用来定义类，后面跟的是类名
        B:main方法的格式是固定的：
            public static void main(String[] args) {

            }
        C:输出语句的格式是固定的：
            System.out.println("HelloWorld");
            "HelloWorld"这个内容是可以改变的
*/
</pre></br>
### 1.4 常量
执行过程中值不变
### 1.5 变量
格式：数据类型 变量名 = 初始化值
### 1.6 数据类型
![](https://alleniverson.gitbooks.io/java-basic-introduction/content/%E7%AC%AC2%E7%AB%A0%20Java%E7%BC%96%E7%A8%8B%E5%9F%BA%E7%A1%80/images/java_basic_35.png)
![](https://alleniverson.gitbooks.io/java-basic-introduction/content/%E7%AC%AC2%E7%AB%A0%20Java%E7%BC%96%E7%A8%8B%E5%9F%BA%E7%A1%80/images/java_basic_36.png)
<pre>Java语言的整型常量默认为int型，声明long型常量可以后加‘ l ’或‘ L ’ ，如:int i1 = 600; //正确     long l1 = 88888888888L; //必须加l否则会出错
Java 浮点型常量默认为 double 型，声明一个常量为 float 型，则需在数字后面加 f 或 F ，如：double d = 12345.6; //正确 float f = 12.3f; //必须加f否则会出错
char 型数据用来表示通常意义上的“字符”,字符常量为用单引号括起来的单个字符，例如：char ch1= 'a'; char ch2='中';
boolean 类型数据只允许取值 true 或 false ，不可以 0 或非 0 的整数替代 true 和 false ，这点和C语言不同。</pre></br>
#### 1.6.1 变量作用域：
* <b>作用域</b> 变量定义在哪个大括号内，它就在这个大括号内有效。 并且，在同一个大括号内不能同时定义同名的变量。
* <b>初始化值</b> 没有初始化值的变量不能直接使用。 你只要在使用前给值就行，不一定非要在定义的时候立即给值。 推荐在定义的时候给值。
#### 1.6.2 类型转换
* 默认转换条件：第一是两种数据类型彼此兼容，第二是目标类型的取值范围大于源类型的取值范围。</br>
               e.g.: (byte，short，char)-->int-->long-->float-->double
* 强制类型转换：在数字前加括号
               e.g.: int x = (int)34.56 + (int)11.2;  // 丢失精度
                     double y = (double)x + (double)10 + 1;  // 提高精度
### 1.7 运算符
括号级别最高，逗号级别最低，单目 > 算术 > 位移 > 关系 > 逻辑 > 三目 > 赋值
## 2 控制语句
## 3 方法
格式：<pre>修饰符 返回值类型 方法名(参数类型 参数名1，参数类型 参数名2…) {
     函数体;
     return 返回值;
 }</pre>
 ## 4 数组
### 4.1 数组定义
格式：</br>
* ` 格式1：数据类型[] 数组名; `
* ` 格式2：数据类型 数组名[]; `
* ` 注意：这两种定义做完了，数组中是没有元素值的 `
### 4.2 数组初始化
Java中的数组必须先初始化,然后才能使用。初始化就是为数组分配内存，为各个数组元素赋值。
* 数组的初始化方式
* 动态初始化：初始化时只指定数组长度，由系统为数组分配初始值。
* 静态初始化：初始化时指定每个数组元素的初始值，由系统决定数组长度。
### 4.3 格式：
* 数据类型[] 数组名 = new 数据类型[数组长度]; e.g.:  int[] arr = new int[3];
### 4.4 内存分配
* 栈：存储局部变量
* 堆：存储new后的结果
* 方法区
* 本地方法区
* 寄存器
![](https://alleniverson.gitbooks.io/java-basic-introduction/content/%E7%AC%AC2%E7%AB%A0%20Java%E7%BC%96%E7%A8%8B%E5%9F%BA%E7%A1%80/images/java_basic_19.png)

