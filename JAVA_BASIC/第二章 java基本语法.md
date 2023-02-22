**第二章 java基本语法**

- **关键词keyword；保留字reservedword**



![](./picture/image_1.368b5acf.png)



![](./picture/image_2.7197b5ea.png)



![](./picture/image_3.b2add35c.png)



保留字：

- **保留字：**
  - 现有Java版本尚未使用， 但以后版本可能会作为关键字用。自己命名标识符时要避免使用这些保留字
  - goto 、 const

- **标志符identifier（不可通过）**
  - 由26个英文字母大小写， 0-9 ， \_或 $ 组成
  - 数字不可以开头。
  - 不可以使用关键字和保留字，但能包含关键字和保留字。
  - Java中严格区分大小写，长度无限制。
  - 标识符不能包含空格
  - 采用unicode字符集

- **命名规范（可通过）**
  - 包名：多单词组成时所有字母都小写：xxxyyyzzz
  - 类名、接口名：多单词组成时，所有单词的首字母大写：XxxYyyZzz
  - 变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写：xxxYyyZzz
  - 常量名：所有字母都大写。多单词时每个单词用下划线连接：XXX\_YYY\_ZZZ

- **变量variable**
  - 变量类型+变量名+存储值
  - 必须先声明并赋值再使用
  - 在作用域内有效
  - 分类：

  ![](./picture/image_4.2780dc3f.png)

  

  ![](./picture/image_5.df1beb4c.png)

  - 声明long型常量须后加‘l’或‘L’
  - 整型一般默认int
  - float 精确7位 声明常量后面加f或者F 数值范围比long还大
  - double 精确15位 一般默认浮点为double
  - ![](./picture/image_6.a6ff9c23.png)

  

  ![](./picture/image_7.efe20751.png)

  

  ![](./picture/image_8.5753f4a3.png)

  

  ![](./picture/image_9.d9d5c5dd.png)

  - char 2字节 unicode编码
  - ![](./picture/image_10.b2a346a3.png)

  

  ![](./picture/image_11.b9618a64.png)

  - 直接使用 Unicode 值来表示字符型常量：‘\\uXXXX’。其中，XXXX代表一个十六进制整数。如：\\u000a表示\\n。
  - ASCII码： 上个世纪60年代， 美国制定了一套字符编码， 对英语字符与二进制位之间的关系， 做了统一规定。 这被称为ASCII码。 ASCII码一共规定了128个字符的编码， 比如空格“SPACE”是32（二进制00100000）， 大写的字母A是65（二进制01000001）。 这128个符号（包括32个不能打印出来的控制符号）， 只占用了一个字节的后面7位， 最前面的1位统一规定为0。
  - Unicode： 一种编码，将世界上所有的符号都纳入其中。每一个符号都给予一个独一无二的编码，使用 Unicode 没有乱码的问题。只规定了符号的二进制代码，却没有规定这个二进制代码应该如何存储：无法区别 Unicode 和 ASCII
  - UTF-8 是在互联网上使用最广的一种 Unicode 的实现方式。一种变长的编码方式。它可以使用 1-6 个字节表示一个符号，根据不同的符号而变化字节长度
    - Uncidoe 字符集≠UTF-8 编码方式
    - Unicode 只是定义了一个庞大的、全球通用的字符集，并为每个字符规定了唯一确定的编号，具体存储成什么样的字节流，取决于字符编码方案。推荐的 Unicode 编码是 UTF-16 和UTF-8。
    - 常见 CharSet 有： GBK、 GB2312、 US-ASCII、 ISO-8859-1、 UTF-8、 UTF-16BE、 UTF-16LE、 UTF-16
    -        // 编译 `javac -encoding utf-8 test2.java`
    -    // 运行 `java -Dfile.encoding=”utf-8” test2`
  - boolean: true false
  - 基本数据类型转换：
    - byte,char,short ->int ->long -> float -> double
    - 容量小的类型自动转换为容量大的数据类型。
    - byte,short,char之间不会相互转换，他们三者在计算时首先转换为int类型。
    - 强制转换 （int） i2，会有精度损失
    - boolean类型不可以转换为其它的数据类型。但可以和String连接运算后强制转换为string
  - 字符串String
    - String不是基本数据类型，属于引用数据类型
    - 当把任何基本数据类型的值和字符串(String)进行连接运算时(+)， 基本数据类型的值将自动转化为字符串(String)类型
    - char之间的加法只能是算数计算
    - 字符串不能直接转换为基本类型， 但通过基本类型对应的包装类则可以实现把字符串转换成基本类型
    - e.g. `String a = “43”; int i = Integer.parseInt(a);`

- **进制**
  - binary：0b 0B
  - octal: 0
  - hexadecimal: 0x 0X

- **binary**
  - 二进制的整数有如下三种形式：
    - 原码：直接将一个数值换成二进制数。最高位是符号位
    - 负数的反码：是对原码按位取反，**只是最高位（符号位）确定为1**。
    - 负数的补码：其反码加1
    - **转换的时候最高位不动，0就是正数，1就是负数**
  - **计算机以二进制补码的形式保存所有的整数**
    - 正数的原码、反码、补码都相同
    - 负数的补码是其反码+1
    - 这样就可以只用加法来表示减法了
  - 转换function：
    - `Integer.toBinaryString(60)`
    - `Integer.toHexString()`

- **运算符**
  - 算数运算符：

  ![](./picture/image_12.e9389c94.png)

  

  ![](./picture/image_13.533a682f.png)

  - 如果对负数取模，可以把模数负号忽略不记，如： 5%-2=1。 但被模数是负数则不可忽略。取模运算的结果不一定总是整数
- 对于除号“/”，它的整数除和小数除是有区别的：整数之间做除法时，只保留整数部分而舍弃小数部分。
  - 赋值运算符： =，+=, -=, \*=, /=, %=
  - 比较运算符：

  ![](./picture/image_14.cefdf1a1.png)

  

  ![](./picture/image_15.eb277d0f.png)

  - \== 还可以使用在其他引用类型变量之间
  - 逻辑运算符：

  ![](./picture/image_16.b6c6e900.png)

  

  ![](./picture/image_17.b5aefeae.png)

  - &”和“&&”的区别：
    - 单&时，左边无论真假，右边都进行运算；
    - 双&时，如果左边为真，右边参与运算，如果左边为假，那么右边不参与运算。

- “|”和“||”的区别同理， ||表示：当左边为真，右边不参与运算
  - 位运算符：

  ![](./picture/image_18.7e312c95.png)

  

  ![](./picture/image_19.8650e867.png)

  

  ![](./picture/image_20.5aa6a781.png)

  

  ![](./picture/image_21.c30ee649.png)

  

  ![](./picture/image_22.226f8f81.png)

  

  ![](./picture/image_23.69d211e0.png)

  

  ![](./picture/image_24.db50f035.png)

  

  ![](./picture/image_25.62781926.png)

  

  ![](./picture/image_26.dd48b03f.png)

  

  ![](./picture/image_27.252d29fa.png)

  

  ![](./picture/image_28.c7fc0d3b.png)

  

  ![](./picture/image_29.cf8d638f.png)

  - 位运算是直接对整数的二进制进行的运算
- 每项往左移一位，就\*一个2；右移，除以一个2  21<<2 =84
- 负数也一样  -21<<2 = -84
- m = k ^ n = (m ^ n) ^ n = m
- 异或满足交换律和结合律 x^y^x = (x^x)^y = 0^y = y
- 0^N = N N^N = 0
- 题目：2\*8的最高效实现方式：2<<3 ; 8<<1
  - 三元运算符：
    - n = （条件表达式）？表达式1：表达式2
    - 两个表达式要求是一致的，被赋值的变量要和表达式类型一致
  - 运算符优先级:

  ![](./picture/image_30.bebfad47.png)

  

  ![](./picture/image_31.2f0b96f8.png)

  - 只有单目运算符、三元运算符、赋值运算符是从右向左运算的。

- **从键盘获取不同类型的变量：需要使用Scanner类**
  - 1\. `import java.util.Scanner;`
  - 2\. Scanner的实例化：`Scanner scan = new Scanner(System.in);`
  - 3\. 调用Scanner类的相关方法, 来获取指定类型的变量：`scan.nextInt();scan.nextDouble();`
  - 4\. char没有提供方法，只能获得一个字符串
  - String a = scan.next();
  - char c = a.charAt(index); //获取索引为0位置的字符
  - `string.equals("...")`

- **随机数生成：**
  - Math类中的random方法：Math.random()返回一个\[0.0,1.0)的数
  - 生成\[a,b\]的随机数：(int)(Math.random() \* (b - a + 1) + a)

- **程序流程控制**
  - 顺序结构
    - 定义变量采用合法的前向引用
  - 分支结构
    - if-else
      - 当多个条件是“互斥”关系时，条件判断语句及执行语句间顺序无所谓
      - 当多个条件是“包含”关系时，“小上大下 / 子上父下”
      - if - else : 就近原则
    - switch-case
      - switch(表达式)中表达式的值必须是下述几种类型之一： byte， short，char， int， 枚举 (jdk 5.0)， String (jdk 7.0)；
      - case子句中的值必须是常量
      - 如果没有break，程序会顺序执行到switch结尾
  - 循环结构
    - 初始条件+循环条件+循环体+迭代条件
    - for
      - 初始化部分可以声明多个变量，但必须是同一个类型，用逗号分隔
      - 可以有多个变量更新，用逗号分隔
    - while
      - while(){
      - }
    - Do-while

    ```java
     do{
      Pass;
    }while();
    ```
    * `break` & `continue`
    * 作用在最近的loop
    * 标签:结束特定循环
      ```java
      label：for(;;) {
        for(;;) {
          break label;
          // continue lable;
        }
      }
  * return： 结束一个方法，返回特定值 

* 其他method
  * String - readKeyBoard()

