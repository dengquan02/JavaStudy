# Java基础



[TOC]

## 第 1 章 内容介绍

## 第 2 章 Java概述

### 2.3 Java技术体系平台

![image-20221031052211427](https://gitee.com/dq-agj/imags/raw/master/img/Java%E6%8A%80%E6%9C%AF%E4%BD%93%E7%B3%BB%E5%B9%B3%E5%8F%B0.png)

### 2.4 Java重要特点

- Java 语言是面向对象的（**oop**）
- Java 语言是健壮的。Java 的强类型机制、异常处理、垃圾的自动收集等是 Java 程序健壮性的重要保证
- Java 语言是**跨平台性**的。【即: 一个编译好的.class 文件可以在多个系统下运行，这种特性称为跨平台】
- Java 语言是解释型的
  - 解释性语言：Javascript，PHP，Java（编译后的代码，不能直接被机器执行,需要解释器来执行）
  - 编译性语言：c / c++（编译后的代码, 可以直接被机器执行）

### 2.6 Java 运行机制及运行过程

Java 核心机制 - Java 虚拟机 【JVM -  Java Virtual Machine】

- JVM是一个虚拟的计算机，具有指令集并使用不同的存储区域。负责执行指令，管理数据、内存、寄存器，包含在JDK中
- 对于不同的平台，有不同的虚拟机
- Java虚拟机机制屏蔽了底层运行平台的差别，实现了“一次编译，到处运行”

![image-20221031052858959](https://gitee.com/dq-agj/imags/raw/master/img/Java%E8%BF%90%E8%A1%8C%E6%9C%BA%E5%88%B6.png)

### 2.7 什么是 JDK，JRE

**JDK** 基本介绍 

- JDK 的全称（Java Development Kit —— Java 开发工具包) ，提供给 Java 开发人员使用
- **JDK = JRE + Java 的开发工具** [java, javac,javadoc,javap 等] 

**JRE** 基本介绍 

- JRE（Java Runtime Environment —— Java 运行环境）
- **JRE = JVM + Java 的核心类库（Java SE 标准类库）** 
- 如果想要运行一个开发好的Java 程序，计算机中只需要安装 JRE 即可。

### 2.17 注释(Comment)

- 单行注释 // 
- 多行注释 /* */ 
  - 文档注释 /** */   :o: 注释内容可以被 JDK 提供的工具 javadoc 所解析，生成一套以网页文件形式体现的该程序的说明文档																																																																																																																																																																																																																																																																																																																																																																																


### 2.18  Java代码规范

- 类、方法的注释，要以javadoc的方式来写。
- 非Java Doc的注释，往往是给代码的维护者看的，着重告述读者为什么这样写，如何修改，注意什么问题等
- 源文件使用utf-8编码
- 行宽度不要超过80字符
- 代码编写次行风格和行尾风格（推荐）



## 第 3 章 变量

### 3.6 数据类型

![image-20221031054025333](https://gitee.com/dq-agj/imags/raw/master/img/Java%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B.png)

Java的整型常量（具体值）默认为int型，声明 long 型常量须后加 l 或 L 

Java的浮点型常量（具体值）默认为double型，声明 float 型常量须后加 f 或 F 

- 关于浮点数在机器中存放形式的简单说明，浮点数=符号位+指数位+尾数位
- 尾数部分可能丢失，造成精度损失(小数都是近似值)。

### 3.15 基本数据类型转换

#### 自动类型转换

当Java程序在进行赋值或者运算时，精度小的类型自动转换为精度大的数据类型，这个就是自动类型转换。

![image-20221031054602900](https://gitee.com/dq-agj/imags/raw/master/img/Java%E8%87%AA%E5%8A%A8%E7%B1%BB%E5%9E%8B%E8%BD%AC%E6%8D%A2.png)

- 有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的那种数据类型，然后再进行计算
- 把精度（容量）大的数据类型赋值给精度（容量）小的数据类型时，报错；反之就会进行自动类型转换
- （byte, short）和char之间不会相互自动转换
- byte，short，char 三者在计算时首先转换为 int 类型
- boolean 不参与自动类型转换
- 自动提升原则：表达式结果的类型自动提升为操作数中最大的类型

#### 强制类型转换

自动类型转换的逆过程，将容量大的数据类型转换为容量小的数据类型。使用时要加上强制转换符( )，但可能造成精度降低或溢出，格外要注意。

- char类型可以保存int的常量值，但不能保存int的变量值，需要强转

### 3.17 基本数据类型和 String 类型的转换

**基本类型转String类型**

语法：将基本类型的值+""即可

**String类型转基本数据类型**（在将String 类型转成基本数据类型时，要确保String类型能够转成有效的数据）

语法：通过基本类型的包装类调用parseXX方法即可（Integer.parseInt(), Double.parseDouble()）

把字符串的第一个字符得到：字符串.charAt(0)

## 第 4 章 运算符

### 4.2 - 4.6 常见运算符

4.2 算术运算符

4.3 关系运算符

4.4 逻辑运算符

- && 短路与：如果第一个条件为 false，则第二个条件不会判断，最终结果为 false，效率高
- & 逻辑与：不管第一个条件是否为 false，第二个条件都要判断，效率低
- ||短路或：如果第一个条件为 true，则第二个条件不会判断，最终结果为 true，效率高
- | 逻辑或：不管第一个条件是否为 true，第二个条件都要判断，效率低

4.5 赋值运算符

4.6 三元运算符

### 4.7 运算符优先级

![image-20221031055919248](https://gitee.com/dq-agj/imags/raw/master/img/%E8%BF%90%E7%AE%97%E7%AC%A6%E4%BC%98%E5%85%88%E7%BA%A7.png)

### 4.8 标识符的命名规则和规范

**标识符的命名规则**（必须遵守）

- 由26个英文字母大小写，0-9，或$组成
- 数字不可以开头
- 不可以使用关键字和保留字，但能包含关键字和保留字。
- Java中<u>**严格区分大小写**</u>，长度无限制
- 标识符不能包含空格

**标识符命名规范**

- 包名：多单词组成时所有字母都小写：aaa.bbb.ccc 比如 com.hsp.crm
- 类名、接口名：多单词组成时，所有单词的首字母大写：XxxYyyZzz 【大驼峰】 比如：TankShotGame 
- 变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写：xxxYyyZzz【小驼峰，简称 驼峰法】 比如： tankShotGame 
- 常量名：所有字母都大写。多单词时每个单词用下划线连接：XXX_YYY_ZZZ 比如：定义一个所得税率 TAX_RATE 

### **4.27 原码、反码、补码（重点 难点）**

- 二进制的最高位是符号位：0表示正数，1表示负数
- 正数的源码，反码，补码都一样（三码合一）
- 负数的反码 = 原码符号位不变，其他位取反；负数的补码 = 反码 + 1
- 0的反码，补码都是0
- Java没有无符号数
- 计算机都是以**补码的方式来运算**的；我们看运算结果要看**原码**

### 4.28 位运算符

Java 中有 7 个位运算：

1. 按位与 &
2. 按位或 |
3. 按位异或 ^
4. 按位取反 ~
5. 算术右移 >> ：低位溢出，符号位不变，并用符号位补高位
6. 算术左移 << ：符号位不变，低位补0
7. 逻辑右移（无符号右移） >>> ：低位溢出，高位补0（特别说明：没有 <<< 符号）



## 第 5 章 程序控制结构



## 第 6 章 数组、排序和查找



## 第 7 章 面向对象编程（基础部分）

### 7.1 类与对象

**Java 内存的结构分析**

栈： 一般存放基本数据类型（局部变量）

堆： 存放对象（Cat cat，数组等）

方法区：常量池（常量，比如字符串），类加载信息

**类和对象的内存分配机制（重要）**

![image-20221031043609894](https://gitee.com/dq-agj/imags/raw/master/img/%E7%B1%BB%E5%92%8C%E5%AF%B9%E8%B1%A1%E7%9A%84%E5%86%85%E5%AD%98%E5%88%86%E9%85%8D%E6%9C%BA%E5%88%B6.png)

#### **Java 创建对象的流程分析**

![image-20221031050548336](https://gitee.com/dq-agj/imags/raw/master/img/%E5%AF%B9%E8%B1%A1%E5%88%9B%E5%BB%BA%E7%9A%84%E6%B5%81%E7%A8%8B%E5%88%86%E6%9E%90.png)

### 7.2 成员方法

**方法的调用机制原理**

![](https://gitee.com/dq-agj/imags/raw/master/img/方法的调用机制原理.png)

### 7.3 成员方法传参机制(非常非常重要)

基本数据类型的传参机制：传递的是值(值拷贝)，形参的任何改变不影响实参！

引用数据类型的传参机制：引用类型传递的是地址（传递也是值，但是值是地址），可以通过形参影响实参！

### 7.4 方法递归调用(非常非常重要，比较难)

### 7.5 方法重载(Overload)

Java 中允许同一个类中，多个同名方法的存在，但要求形参列表不一致！

- 方法名：必须相同
- 形参列表：必须不同（形参类型或个数或顺序，至少有一样不同，参数名无要求）
- 返回类型：无要求

### 7.6 可变参数

Java 允许将同一个类中多个同名同功能但参数个数不同的方法，封装成一个方法，可以通过可变参数实现。

```java
访问修饰符 返回类型 方法名(数据类型... 形参名) {
    
}
```

- 可变参数的实参可以为0个或任意多个，也可以为数组
- 可变参数的本质就是数组
- 可变参数可以和普通类型的参数一起放在形参列表，但必须保证可变参数在最后
- 一个形参列表中只能出现—个可变参数

### 7.7 作用域

Java中作用域的分类：

- **全局变量**：类的属性，作用域为整个类体
- **局部变量**：除了属性之外的其他变量，作用域为定义它的代码块中！（我们说的局部变量一般是指在成员方法中定义的变量）

:yum: 全局变量（属性）可以不赋值，直接使用，因为有默认值，局部变量必须赋值后才能使用，因为没有默认值。

### 7.8 构造方法/构造器

```java
[修饰符] 方法名(形参列表){
    方法体;
}
```

- 在创建对象时，系统会自动的调用该类的构造器完成对象的初始化
- 一个类可以定义多个不同的构造器，即构造器重载
- 如果没有定义构造器，系统会自动给类生成一个默认无参构造器
- 一旦定义了自己的构造器，默认的构造器就覆盖了，就不能再使用默认的无参构造器，除非显式的定义一下

### 7.10 this 关键字

- this 关键字可以用来访问本类的属性、方法、构造器
- 可用于区分当前类的属性和局部变量
- 访问构造器语法：`this(参数列表)`；注意只能在构造器中使用（即只能在构造器中访问另外一个构造器，必须放在第一条语句）
- this 不能在类定义的外部使用，只能在类定义的方法中使用。



## 第 8 章 面向对象编程（中级部分）

### 8.5 访问修饰符

Java 提供四种访问控制修饰符号，用于控制方法和属性(成员变量)的访问权限（范围）: 

|               | 同类 | 同包 | 子类 | 不同包 |
| ------------- | ---- | ---- | ---- | ------ |
| **public**    | √    | √    | √    | √      |
| **protected** | √    | √    | √    |        |
| **默认**      | √    | √    |      |        |
| **private**   | √    |      |      |        |

只有默认的和public才能修饰类，并且遵循上述访问权限的特点。

### 8.6 面向对象编程的三大特征 —— 封装

封装（encapsulation）就是把抽象出的数据【属性】和对数据的操作【方法】封装在一起，数据被保护在内部，程序的其它部分只有通过被授权的操作，才能对数据进行操作。

**封装的理解和好处**

- 隐藏实现细节
- 可以对数据进行验证，保证安全合理

**封装的实现步骤（三步）**

1. 将属性进行私有化 private
2. 提供公共的（public）set方法，用于对属性赋值
3. 提供公共的（public）get方法，用于获取属性的值

### 8.8 面向对象编程的三大特征 —— 继承

当多个类存在相同的属性和方法时,可以从这些类中抽象出父类，在父类中定义这些相同的属性和方法，所有的子类不需要重新定义这些属性和方法，只需要通过extends来声明继承父类即可。

![image-20221031025617642](https://gitee.com/dq-agj/imags/raw/master/img/%E7%BB%A7%E6%89%BF%E7%A4%BA%E6%84%8F%E5%9B%BE.png)

**继承给编程带来的便利** 

- 代码的复用性提高了
- 代码的扩展性和维护性提高了

**继承的深入讨论/细节问题**

1. 子类的构造器默认情况下总会去调用父类的<u>无参构造器</u>，如果父类没有提供无参构造器，则必须在子类的构造器中用 **super** 去指定使用父类的哪个构造器完成对父类的初始化工作，否则编译不会通过。
2. super() 和 this() 都只能放在构造器**第一行**，因此这两个方法不能共存在一个构造器
3. Java 所有类都是 Object 类的子类，Object 是所有类的基类
4. 子类最多只能继承一个父类（指直接继承），即 Java 中是**单继承机制**

#### **继承的本质分析（重要）**

当子类对象创建好后，建立查找的关系。***子类对象.属性（子类对象.方法）***

1. 首先看子类是否有该成员
2. 如果子类有这个成员，并且可以访问，则返回信息
3.  如果子类没有这个成员，就看父类有没有该成员（如有，并且可以访问，就返回信息）
4.  如果父类没有就按照 3 的规则，继续找上级父类，直到 Object...

查找过程中，如果找到了但是不能访问（无权限）， 则报错 cannot access ；如果没有找到，则提示不存在

<img src="https://gitee.com/dq-agj/imags/raw/master/img/%E7%BB%A7%E6%89%BF%E7%9A%84%E5%86%85%E5%AD%98%E5%B8%83%E5%B1%80.png" alt="image-20221031030930923"  />

### 8.9 super关键字

super 代表父类的引用，用于访问父类的属性、方法、构造器。

1. 访问父类的属性，但不能访问父类的private属性

   *super.属性名*;

2. 访问父类的方法，不能访问父类的private方法
   *super.方法名(参数列表);*

3. 访问父类的构造器（只能放在构造器的第一句，只能出现一句！）
   *super(参数列表);* 

**super 给编程带来的便利**：分工明确，父类属性由父类初始化，子类属性由子类初始化

### 8.10 方法重写/覆盖（override）

- 子类方法的**形参列表**，**方法名称**和父类方法的完全一样
- 子类方法的**返回类型**和父类方法返回类型一样，或者是父类方法返回类型的子类（eg：父类方法返回类型Object，子类方法返回类型String）
- 子类方法不能缩小父类方法的访问权限

**方法重写和重载的比较**

| 名称             | 范围   | 方法名 | 形参列表                       | 返回类型                                                     | 修饰符                             |
| ---------------- | ------ | ------ | ------------------------------ | ------------------------------------------------------------ | ---------------------------------- |
| 重载（overload） | 本类   | 一样   | 类型、个数、顺序至少有一个不同 | 无要求                                                       | 无要求                             |
| 重写（override） | 父子类 | 一样   | 相同                           | 子类重写的方法，返回类型和父类方法返回类型一致，或者是其子类 | 子类方法不能缩小父类方法的访问权限 |



### 8.11 面向对象编程的三大特征 —— 多态

多态：方法或对象具有多种形态。多态是建立在封装和继承基础之上的。

1. 方法的多态 —— 重写和重载

2. 对象的多态 （核心，困难，重点）

   - 一个对象的编译类型和运行类型可以不一致

   - 编译类型在定义对象时就确定了，不能改变，而运行类型是可以变化的

#### 多态的向上转型

- 本质：父类的引用指向了子类的对象
- 语法：父类类型引用名 = new 子类类型;
- 特点：编译类型看左边，运行类型看右边。调用父类中的所有成员（需遵守访问权限），不能调用子类中特有成员；最终运行效果看子类

:smiley: 能调用哪些成员是由编译类型来决定，最终运行效果看子类（运行类型）的具体实现。

#### 多态的向下转型

- 语法：子类类型引用名 = （子类类型）父类引用
- 只能强转父类的引用，不能强转父类的对象
- 要求父类的引用必须指向的是当前目标类型的对象
- 当向下转型后，可以调用子类类型中所有的成员

:smiley: 属性没有重写之说！属性的值看编译类型

**:smiley: instanceof** 比较操作符，用于判断对象的运行类型是否为 XX 类型或 XX 类型的子类型

#### **Java 的动态绑定机制（非常非常重要）**

- 当调用对象方法（非静态）的时候，该方法会和该对象的内存地址/运行类型绑定
- 当调用对象属性时，没有动态绑定机制，哪里声明就哪里使用

**多态的应用**

- 多态数组：数组的定义类型为父类类型，里面保存的实际元素类型为子类类型
- 多态参数：方法定义的形参类型为父类类型，实参类型允许为子类类型

### 8.12 Object类详解

#### equals方法

**==**是一个比较运算符，既可以判断基本类型，又可以判断引用类型。如果判断基本类型，判断的是值是否相等；如果判断引用类型，判断的是地址是否相等，即判定是不是同一个对象

**equals**是Object类中的方法，只能判断引用类型，默认判断的是地址是否相等，子类中往往重写该方法，用于判断内容是否相等。

#### hashcode方法

- 提高具有哈希结构的容器的效率
- 两个引用，如果指向的是同一个对象，则哈希值肯定是一样的；如果指向的是不同对象，则哈希值是不一样的 
- 哈希值主要根据地址号来的， 不能完全将哈希值等价于地址

#### toString方法

- 默认返回：全类名+@+哈希值的十六进制，子类往往重写 toString 方法，用于返回对象的属性信息
- 打印对象或拼接对象时，都会自动调用该对象的 toString 形式

#### finalize方法

- 当对象被回收时，系统自动调用该对象的 finalize 方法。子类可以重写该方法，做一些释放资源的操作
- 什么时候被回收：当某个对象没有任何引用时，则 jvm 就认为这个对象是一个垃圾对象，就会使用垃圾回收机制来销毁该对象，在销毁该对象前，会先调用 finalize 方法
- 垃圾回收机制的调用，是由系统来决定（即有自己的 GC 算法），也可以通过 System.gc() 主动触发垃圾回收机制



## 第 10 章 面向对象编程（高级部分）

### 10.1 类变量与类方法

- **类变量（静态变量）**是同一个类所有对象共享，而实例变量是每个对象独享的
- 类变量的生命周期是随类的加载开始，随着类消亡而销毁

- **类方法（静态方法）**只能访问静态成员，非静态的方法可以访问静态成员和非静态成员。（必须遵守访问权限）
- 类方法和普通方法都是随着类的加载而加载，将结构信息存储在方法区
- 类方法中不允许使用和对象有关的关键字，比如this和super

:confused: **JAVA父类的静态方法能否被子类重写？（答：能被继承，但不可以重写）**

>  在编译时所分配的内存会一直存在（不会被回收），直到程序退出内存才会释放这个空间，在实例化之前这个方法就已经存在于内存，跟类的对象没什么关系。子类中如果定义了相同名称的静态方法，并不会重写，而应该是在内存中又分配了一块给子类的静态方法，没有重写这一说，只是单纯的名字重复了。
>
> 静态方法是在编译时使用了编译类信息，进行静态绑定的。它和对象无关，而和类有关。
>
> ```java
> // 借此加深对于 动态绑定机制 的理解
> 
> public class test {
>        public static void main(String[] args) {
>            Fu fu = new Zi();
>            //method为非静态方法，而fu运行类型为Zi，因此调用Zi的method
>            fu.method();//"子类的一般方法"
>            //show为静态方法，而fu编译类型为Fu，因此调用Fu的show
>            fu.show();//"父类的静态方法"
>            // show2是非静态方法，调用时该方法会和运行类型（Zi）绑定；
>            // 进入到show2方法体后，由于此时已经绑定Zi，所以调用的是Zi的show 
>            fu.show2();//"子类的静态方法"   
>        }
> }
> 
> class Fu {
>        public void method() {
>            System.out.println("父类的一般方法");
>        }
>        public static void show() {
>            System.out.println("父类的静态方法");
>        }
>        public void show2() {
>            show();
>        }   
> }
> 
> class Zi extends Fu {
>        public void method() {
>            System.out.println("子类的一般方法");
>        }
>        public static void show() {
>            System.out.println("子类的静态方法");
>        }
>        public void show2() {
>            show();
>        }
> }
> ```



### 10.2 main方法

```java
public static void main(String[] args)
```

- main方法由java虚拟机调用，所以权限需要是public
- 执行main方法时不必创建对象，所以是static方法
- 接收String[]，args数组保存执行java命令时传递给所运行的类的参数（java 执行的程序 arg1 arg2 arg3）

### 10.3 代码块

```java
[修饰符] {
	代码
};
```

修饰符可选，要写也只能写static。静态代码块只能直接调用静态成员(静态属性和静态方法)，普通代码块可以调用任意成员。

------

#### **类什么时候被加载**

- 创建对象实例时（new）
- 使用类的静态成员（静态变量，静态方法）时
- 子类被加载，父类也会加载并且先加载

------

 :smile: 构造器的最前面其实隐含了super()和调用普通代码块、普通属性初始化

```java
class A {
    public void a() {
        // super
        // 调用普通代码块、普通属性初始化
        xxxx;
    }
}
```

------

#### **创建一个子类对象实例时，执行顺序**

1. 类加载（只加载一次）
   1. 父类的静态代码块和静态属性（优先级一样，按定义顺序执行）
   2. 子类的静态代码块和静态属性（优先级一样，按定义顺序执行）
2. 创建对象
   1. 父类的普通代码块和普通属性初始化(优先级一样，按定义顺序执行)
   2. 父类的构造方法
   3. 子类的普通代码块和普通属性初始化(优先级一样，按定义顺序执行)
   4. 子类的构造方法

### 10.4 单例设计模式

类的单例（Singleton）模式，就是采取一定的方法保证在整个的软件系统中，对**某个类只能存在一个对象实例**，并且该类只提供一个取得其对象实例的方法。

**饿汉式**

1. 构造器私有化 --> 防止直接new
2. 类的内部**创建**静态对象
3. 提供一个公共的静态方法，返回对象

```java
class GirlFriend {
    private String name;
    //为了能够在静态方法中，返回 gf对象，需要将其修饰为static
    private static GirlFriend gf = new GirlFriend("小红红");
    
    private GirlFriend(String name) {
        this.name = name;
    }

    public static GirlFriend getInstance() {
        return gf;
    }
}
```

**懒汉式**

1. 构造器私有化 --> 防止直接new
2. **定义**一个静态对象
3. 提供一个公共的静态方法，返回对象

```java
class Cat {
    private String name;
    private static Cat cat ; //默認是null

    //只有當用戶使用getInstance時，才返回cat對象, 後面再次調用時，會返回上次創建的cat對象，而保證了單例
    private Cat(String name) {
        this.name = name;
    }
    
    public static Cat getInstance() {
        if(cat == null) {//如果還沒有創建cat對象
            cat = new Cat("小可愛");
        }
        return cat;
    }
}
```

**饿汉式 VS 懒汉式**

- 二者最主要的区别在于创建对象的时机不同：饿汉式是在类加载就创建了对象实例，而懒汉式是在使用时才创建。
- 懒汉式存在线程安全问题。
- 饿汉式存在浪费资源的可能。（因为在类加载时就创建）

### 10.5 final 关键字

final可以修饰类、方法、属性和局部变量。使用场景：

1. 当不希望类被继承时
2. 当不希望父类的某个方法被子类覆盖/重写（Override）
3. 当不希望类的某个属性的值被修改
4. 当不希望某个局部变量被修改

- final修饰的<u>属性</u>又叫常量，一般用 XX_XX_XX 来命名
- final修饰的<u>属性</u>在定义时，必须赋初值，并且以后不能再修改，赋值可以在如下位置之一：①定义时；②在构造器中；③在代码块中
- 如果final修饰的<u>属性</u>是静态的，则初始化的位置只能是：①定义时；②在静态代码块中
- final不能修饰构造器
- final和static往往搭配使用，效率更高，不会导致类加载。（底层编译器做了优化处理）
- 包装类（Integer，Double，Float，Boolean等都是final），String也是final类。

### 10.6 抽象类

**父类方法的不确定性**：当父类的某些方法，需要声明，但是又不确定如何实现时，可以将其声明为抽象方法，那么这个类就是抽象类。一般来说，抽象类会被继承，有其子类来实现抽象方法

- 抽象类不能被实例化
- 抽象类不一定要包含abstract方法；一旦类包含了abstract方法，则这个类必须声明为abstract
- 抽象方法不能有主体，即不能实现
- 如果一个类继承了抽象类，则它必须实现抽象类的所有抽象方法，除非它自己也声明为abstract类
- 抽象方法不能使用 **private**、**final** 和 **static** 来修饰，因为这些关键字都是和重写相违背的。（**仔细思考如何理解**）

### 10.7 抽象类最佳实践-模板设计模式

1. 当功能内部一部分实现是确定的，一部分实现是不确定的，可以把不确定的部分暴露出去，让子类去实现。
2. 编写一个抽象父类，父类提供了多个子类的通用方法，并把一个或多个方法留给其子类实现，就是一种模板（Template）模式。

:exclamation: eg. 有多个类，分别完成不同的任务，要求统计得到各自完成任务的时间。

```java
abstract public class Template { //抽象类-模板设计模式

    public abstract void job();//抽象方法

    public void calculateTime() {//实现方法，调用job方法
        //得到开始的时间
        long start = System.currentTimeMillis();
        job(); //动态绑定机制，调用子类重写的job()
        //得到结束的时间
        long end = System.currentTimeMillis();
        System.out.println("任务执行时间 " + (end - start));
    }
}
```

### 10.8 接口

接口给出一些没有实现的方法，封装到一起，到某个类要使用的时候，再根据具体情况把这些方法实现。

**interface vs 现实中的接口**（我的理解）：

1. 有一接口UsbInterface，定义了一些未实现的接口方法；
2. MP3类implements该接口，就相当于MP3长出了一个USB接口，并实现了对应的接口功能；
3. 而Computer类中定义的方法 work(USBInterface usbInterface) 就相当于电脑提供了对应的一个插槽；
4. 当调用该方法时相当于这样一个带USB接口的MP3插入到电脑中，电脑通过work的方法实现去调用MP3类实现的接口功能。

```java
interface 接口名 {
    属性;
    抽象方法;
}

class 类名 implements 接口名 {
    自己属性;
    自己方法;
    接口的抽象方法;
}
```

> 小结：接口是更加抽象的抽象类，抽象类里的方法可以有方法体，接口里的所有方法都没有方法体【jdk7.0】。接口体现了程序设计的多态和高内聚低偶合的设计思想。
>
> 特别说明：**jdk8.0**后接口类可以有**静态（static）方法**，**默认（default）方法**，也就是说接口中可以有方法的具体实现

> > **默认方法的典型应用**：无需修改实现类的代码，就能提供额外的功能。
> >
> > 在实际开发中，一个接口往往会有多个实现类，如果后期往接口中添加一个方法，那么所有的实现类都会被强制性要求实现新添加的方法，否则编译报错，一个两个实现类还能改一改，十个八个就太麻烦了。这时就轮到默认方法登场了，实现类无需主动去实现它，就能直接访问，因而也就不需要修改所有实现类的代码了。
> >
> > 在某些情况下，如果一个类实现了两个接口（或者一个接口继承了两个接口），并且这两个接口中都包含相同的默认方法，需要手动去<u>重写</u>该方法，在方法体中<u>指定调用</u>哪个接口中的默认方法（语法：`接口名.super.默认方法名()`）
> >
> > **接口静态方法**：提供一个简单的机制，它允许我们将相关方法放在一个单独的地方而不必另外创建一个对象，这样可以提高代码的内聚度。

**注意事项和细节**

- 接口不能被实例化
- 接口中所有的方法是**public**方法（不过在实现接口时，必须声明public），接口中抽象方法，可以不用**abstract**修饰。`void aaa();`实际上是`public abstract void aaa();`
- 一个普通类实现接口，就必须将该接口的所有方法都实现；抽象类实现接口，可以不用实现接口的方法。
- 一个类同时可以实现多个接口
- 接口中的属性，只能是final的，而且是public static final修饰符。比如`int a = 1;`实际上是 `public static final int a = 1;`（必须初始化）
- 接口不能继承其它的类，但是可以继承多个别的接口。eg. `interface A extends B, C {}`

**实现接口 vs 继承类**

当子类继承了父类，就自动拥有父类的功能，如果子类需要扩展功能（该功能父类并不具备），可以通过实现接口的方式扩展。可以理解实现**接口**是对Java**单继承机制**（针对类）的一种补充。

[Java的单继承(extends)机制与多接口(interface)机制]: https://caotc.org/2018/01/02/java-java8-extend-design-thinking/

- 接口和继承解决的问题不同
  - 继承的价值主要在于：解决代码的复用性和可维护性。
  - 接口的价值主要在于：设计，设计好各种规范（方法），让其它类去实现这些方法。
- 接口比继承更加灵活：继承是满足 **is - a** 的关系，而接口只需满足 **like - a** 的关系。
- 接口在一定程度上实现代码<u>解耦</u>【即：接口规范性+动态绑定机制】

**接口的多态特性**

1. 多态参数：方法定义的形参类型为接口类型，实参类型允许为实现了接口的类（<u>向上转型</u>：接口引用可以指向实现了接口的类的对象）
2. 多态数组： 数组的定义类型为接口类型，里面保存的实际元素类型为实现了接口的类；接口的引用不能直接调用实现类中特有的成员，需要<u>向下转型</u>后进行调用。
3. 接口存在<u>多态传递现象</u>：如果 IG 继承了 IH 接口，而 Teacher 类实现了 IG接口，实际上就相当于 Teacher 类也实现了 IH 接口。

### 10.9 内部类

类的五大成员：属性，方法，构造器，代码块，**内部类**。

```java
class Outer { //外部类
    class Inner { //内部类
        
    }
}
class Other { //外部其它类
    
}
```

**内部类的分类**

定义类在局部位置（方法中/代码块） ：(1) 局部内部类；(2) **匿名内部类**

定义在成员位置 ：(1) 成员内部类；(2) 静态内部类

#### 局部内部类

定义在外部类的局部位置，有类名。地位类似局部变量。

- 局部内部类访问外部类的所有成员：直接访问；外部类访问局部内部类的成员：通过创建对象再访问；外部其他类不能访问局部内部类。
- 不能添加访问修饰符；可以用final修饰。
- 作用域：定义它的局部位置（方法体或者代码块中）。
- 如果外部类和局部内部类的成员重名时，默认遵循就近原则，如果想访问外部类的成员，则可以使用 `外部类名.this.成员 `去访问（*<u>外部类名.this</u>* 本质就是外部类的对象）

#### **匿名内部类**

定义在外部类的局部位置，没有类名（实际上系统底层会分配类名）。

```java
new 类或接口(参数列表) {
    类体
};
```
```java
class Outer {
    public void method() {
    //基于接口的匿名内部类
        //需求：想使用IA接口，并创建对象。传统方式是写一个类实现该接口并创建对象，但如果这个类只是使用一次，后面不再使用，可以使用匿名内部类来简化开发。
        //编译类型：IA	运行类型：匿名内部类（Outer$1）
        /*
        	class Outer$1 implements IA {
        		@Override
        		public void cry() {
        			System.out.println("老虎叫唤...");
        		}
        	}
        */
        //底层创建匿名内部类Outer$1，同时创建了 Outer$1 实例，并且把地址返回给 tiger
        IA tiger = new IA() {
            @Override
            public void cry() {
                System.out.println("老虎叫唤...");
            }
        };
        System.out.println("tiger 的运行类型=" + tiger.getClass());
        tiger.cry();
        
    //基于类的匿名内部类
        //编译类型：Father	运行类型：匿名内部类（Outer$2）
        /*
        	class Outer$2 extends Father {
        		@Override
                public void test() {
                    System.out.println("匿名内部类重写了 test 方法");
                }
        	}
        */        
        //底层创建匿名内部类Outer$2，同时创建了 Outer$2 实例，并且把地址返回给 father
        Father father = new Father("jack") {
            //test方法可以不用重写，如果是抽象方法则必须要重写
            @Override
            public void test() {
                System.out.println("匿名内部类重写了 test 方法");
            }
        };
        father.test();
    }
}

interface IA {
    void cry();
}

class Father {
    public Father(String name) {
        System.out.println("接收到 name=" + name);
    }
    
    public void test() {
        
    }
}
```

匿名内部类的最佳实践：当做实参直接传递，简洁高效。

#### 成员内部类

定义在外部类的成员位置，并且没有static修饰。地位类似成员变量/成员方法。

- 可以添加任意访问修饰符

- 作用域：外部类的整个类体

- 外部其他类可以访问成员内部类（前提是满足访问权限）：

  ```java
  public class MemberInnerClass {
  	public static void main(String[] args) {
          Outer outer = new Outer();
          //第一种方式
          Outer.Inner inner1 = outer.new Inner();
          //第二种方式：在外部类中编写一个方法，可以返回Inner对象实例
          Outer.Inner inner2 = outer.getInnerInstance();
      }
  }
  
  public class Outer {
      public class Inner {
          
      }
      public Inner getInnerInstance() {
          return new Inner();
      }
  }
  ```

#### 静态内部类

定义在外部类的成员位置，并且有static修饰。

- 可以直接访问外部类的所有<u>静态</u>成员，但不能直接访问非静态成员

- 外部其他类可以访问静态内部类（前提是满足访问权限）：

  ```java
  public class StaticInnerClass {
  	public static void main(String[] args) {
          Outer outer = new Outer();
          //第一种方式
          Outer.Inner inner1 = new Outer.Inner();
          //第二种方式：在外部类中编写一个方法，可以返回Inner对象实例
          Outer.Inner inner2 = outer.getInnerInstance01();
          Outer.Inner inner3 = Outer.getInnerInstance02();
      }
  }
  
  public class Outer {
      static class Inner {
          
      }
      public Inner getInnerInstance01() {
          return new Inner();
      }
      public static Inner getInnerInstance02() {
          return new Inner();
      }
  }
  ```

- 如果外部类和静态内部类的成员重名时，默认遵循就近原则，如果想访问外部类的成员，则可以使用 `外部类名.成员 `去访问



## 第 11 章 枚举和注解

### 11.5 自定义实现枚举

1. 将构造器私有化，防止直接new
2. 去掉setXxx方法，防止属性被修改
3. 本类内部创建一组 public final static 对象。（为什么加 final：static + final 避免类加载，实现底层优化；final不能防止对象的属性值被修改，因为所修饰的本质上是一个指向对象实例的引用名）

### 11.7 enum 关键字实现枚举

1. 使用关键字 enum 替代 class

2. 使用 `常量名(实参列表);` 替代 `public static final 类名 常量名 = new 类名(实参列表);` （如果使用的是无参构造器，则可以省略()。）

3. 如果有多个常量（对象），使用逗号间隔即可，最后一个有分号结尾

4. 将定义常量对象写在最前面

   :crab: 当使用 enum 关键字开发一个枚举类时，默认会继承 Enum 类（因此不能再继承其他类了），而且是一个 final 类。

### 11.9 enum 常用方法

- toString：Enum 类已经重写过了，返回的是当前对象名，子类可以重写该方法，用于返回对象的属性信息 
- name：返回当前对象名（常量名），子类中不能重写 
- ordinal：返回当前对象的位置号，默认从 0 开始 
- values：返回当前枚举类中所有的常量
- valueOf：将字符串转换成枚举对象，要求字符串必须为已有的常量名，否则报异常！
- compareTo：比较两个枚举常量，比较的就是编号！

### 11.13 基本的 Annotation 介绍

- @Override：限定某个方法，是重写父类方法, 该注解只能用于方法 
- @Deprecated：用于表示某个程序元素(类, 方法等)已过时
- @SuppressWarnings：抑制编译器警告



## 第 12 章 异常 - Exception

### 12.4 异常体系图

<img src="https://gitee.com/dq-agj/imags/raw/master/img/%E5%BC%82%E5%B8%B8%E4%BD%93%E7%B3%BB%E5%9B%BE.png" alt="image-20221209010553622"  />

- 常见运行时异常：

  - NullPointerException 空指针异常

  - ArithmeticException 数学运算异常

  - ArrayIndexOutOfBoundsException 数组下标越界异常

  - ClassCastException 类型转换异常

  - NumberFormatException 数字格式不正确异常

- 常见编译异常：

  - SQLException 操作数据库时，查询表可能发生异常
  - IOException 操作文件时，发生的异常

  - FileNotFoundException 当操作一个不存在的文件时，发生异常

  - ClassNotFoundException 加载类，而该类不存在时，异常
  - EOFException 操作文件，到文件末尾,发生异常

  - IllegalArguementException 参数异常

### 12.8 异常处理

1. **try-catch-finally**：程序员在代码中捕获发生的异常，自行处理

  ![image-20221224165816200](https://gitee.com/dq-agj/imags/raw/master/img/try-catch-finally%20%E5%A4%84%E7%90%86%E6%9C%BA%E5%88%B6%E7%A4%BA%E6%84%8F%E5%9B%BE)

 可以有多个catch语句，捕获不同的异常（进行不同的业务处理），要求父类异常在后，子类异常在前（比如Exception在后，NullPointerException在前)，如果发生异常，只会匹配一个catch。

2. **throws**：将发生的异常抛出，交给调用者（方法）来处理，最顶级的处理者就是JVM

  ![image-20221224165916182](https://gitee.com/dq-agj/imags/raw/master/img/throws%20%E5%A4%84%E7%90%86%E6%9C%BA%E5%88%B6%E7%A4%BA%E6%84%8F%E5%9B%BE)

  throws 关键字后可以是异常列表，即可以抛出多个异常。

- 对于编译异常，程序中必须处理，比如 try-catch 或者 throws；若 f2() 调用 f1() 且 f1() 抛出编译异常，则 f2() 必须要处理这个编译异常。
- 对于运行时异常，程序中如果没有显示处理，默认就是 throws 的方式处理
- 子类重写父类的方法时，对抛出异常的规定：子类重写的方法，所抛出的异常类型要么和父类抛出的异常一致，要么为父类抛出的异常的类型的子类型
- 在throws过程中，如果有方法 try-catch，就相当于处理异常，就可以不必 throws

### 12.11 自定义异常

**自定义异常的步骤**

1. 定义类：自定义异常类名继承 Exception 或 RuntimeException
2. 如果继承 Exception，属于编译异常
3. 如果继承 RuntimeException，属于运行异常（一般来说，继承RuntimeException）

```java
public class CustomException {
    public static void main(String[] args) {
    	int age = 180;
    	//要求范围在 18 – 120 之间，否则抛出一个自定义异常
    	if(!(age >= 18 && age <= 120)) {
    		//这里我们可以通过构造器，设置信息
    		throw new AgeException("年龄需要在 18~120 之间");
    	}
    	System.out.println("你的年龄范围正确.");
    }
}

//自定义一个异常
class AgeException extends RuntimeException {
    public AgeException(String message) {//构造器
    	super(message);
    }
}
```

### 12.12 throw 和 throws 的区别

|        | 意义                     | 位置       | 后面跟的东西 |
| ------ | ------------------------ | ---------- | ------------ |
| throws | 异常处理的一种方式       | 方法声明处 | 异常类型     |
| throw  | 手动生成异常对象的关键字 | 方法体中   | 异常对象     |



## 第 13 章 常用类

### 13.1 包装类

JAVA是面向对象语言，为了实现一切皆对象，于是为8种基本数据类型提供了对应的引用类型

**包装类的分类**

![image-20221226140550133](https://gitee.com/dq-agj/imags/raw/master/img/%E5%8C%85%E8%A3%85%E7%B1%BB%E7%9A%84%E5%88%86%E7%B1%BB)

![image-20221226143857146](https://gitee.com/dq-agj/imags/raw/master/img/%E5%8C%85%E8%A3%85%E7%B1%BB%E7%BB%A7%E6%89%BF%E5%85%B3%E7%B3%BB)

**包装类和基本数据的转换**

```java
//演示int <--> Integer 的装箱和拆箱
//jdk5前是手动装箱和拆箱
int n1 = 100;
//手动装箱 int->Integer
Integer integer = new Integer(n1);
Integer integer1 = Integer.valueOf(n1);
//手动拆箱 Integer -> int
int i = integer.intValue();

//jdk5后，就可以自动装箱和自动拆箱
int n2 = 200;
//自动装箱 int->Integer
Integer integer2 = n2; //底层使用的是 Integer.valueOf(n2)
//自动拆箱 Integer->int
int n3 = integer2; //底层仍然使用的是 intValue()方法
```

Exercise：

```java
Object obj1 = true? new Integer(1) : new Double(2.0);//三元运算符【是一个整体】
System.out.println(obj1);// 1.0
//三元操作符必须要返回一个数据，且类型要确定，不可能条件为真时返回Integer，条件为假时返回Double，编译器是不允许如此的，所以运算的时候，先进行类型的转换，转换为高精度的。

Object obj2;
if(true)
    obj2 = new Integer(1);
else
    obj2 = new Double(2.0);
System.out.println(obj2);//1
//分别计算，不是一个整体
```

**包装类和 String 的相互转换**

```java
//包装类(Integer) -> String
Integer i = 100;//自动装箱
//方式1
String str1 = i + "";
//方式2
String str2 = i.toString();
//方式3
String str3 = String.valueOf(i);

//String -> 包装类(Integer)
String str4 = "12345";
Integer i2 = Integer.parseInt(str4);//使用到自动装箱
Integer i3 = new Integer(str4);//构造器
```

**Integer 类和 Character 类的常用方法**

```java
System.out.println(Integer.MIN_VALUE); //返回最小值
System.out.println(Integer.MAX_VALUE);//返回最大值

System.out.println(Character.isDigit('a'));//判断是不是数字
System.out.println(Character.isLetter('a'));//判断是不是字母
System.out.println(Character.isUpperCase('a'));//判断是不是大写
System.out.println(Character.isLowerCase('a'));//判断是不是小写
System.out.println(Character.isWhitespace('a'));//判断是不是空格
System.out.println(Character.toUpperCase('a'));//转成大写
System.out.println(Character.toLowerCase('A'));//转成小写
```

Integer面试题

```java
Integer i = new Integer(1);
Integer j = new Integer(1);
System.out.println(i == j); //false

/*
1. 如果 i 在 IntegerCache.low ~ IntegerCache.high (-128 ~ 127)，就直接从数组返回
2. 如果不在 -128~127，就直接 new Integer(i)
    public static Integer valueOf(int i) {
        if (i >= IntegerCache.low && i <= IntegerCache.high)
            return IntegerCache.cache[i + (-IntegerCache.low)];
        return new Integer(i);
    }
*/
Integer m = 1; //底层 Integer.valueOf(1);
Integer n = 1;//底层 Integer.valueOf(1);
System.out.println(m == n); //true

Integer x = 128;//底层 Integer.valueOf(128);
Integer y = 128;//底层 Integer.valueOf(128);
System.out.println(x == y); //false

/*
只要有基本数据类型，判断的是值是否相同
*/
Integer i11 = 128;
double i12 = 128;
System.out.println(i11 == i12); //true
```

### 13.2 String 类

**String 类的理解**

![image-20230103234402232](https://gitee.com/dq-agj/imags/raw/master/img/String%E7%B1%BB%E7%9A%84%E7%BB%A7%E6%89%BF%E5%85%B3%E7%B3%BB)

- String 对象用于保存字符串，也就是一组字符序列 
- 字符串的字符使用 Unicode 字符编码，一个字符（不区分字母还是汉字）占两个字节
- String 类实现了接口 Serializable【String 可以串行化：可以保存到文件或网络传输】、接口 Comparable【String 对象可以比较大小】
- String 是 final 类，不能被其他的类继承
- String 有属性 `private final char value[]`；用于存放字符串内容（value 不能指向新的地址，但是单个字符内容是可以变化）

**创建 String 对象的两种方式**

方式一：直接赋值 `String s = "hsp";`

先从常量池查看是否有"hsp"数据空间，如果有，直接指向；如果没有则重新创建，然后指向。s最终指向的是常量池的空间地址。

方式二：调用构造器 `String s2 = new String("hsp");`

先在堆中创建空间，里面维护了value属性，指向常量池的hsp空间（如果常量池没有"hsp"，重新创建）。s2最终指向的是堆中的空间地址。

![image-20221230172846299](https://gitee.com/dq-agj/imags/raw/master/img/String%E7%9A%84%E5%86%85%E5%AD%98%E5%B8%83%E5%B1%80)

intern()最终返回的是常量池的地址（对象）：当调用 intern 方法时，如果池已经包含一个等于此 String对象的字符串（用 **equals(Object)** 方法确定），则返回池中的字符串。否则，将此 String对象添加到池中，并返回此 String 对象的引用。

### 13.3 字符串的特性

- String是一个final类，代表不可变的字符序列。
- 字符串是不可变的。一个字符串对象一旦被分配，其内容是不可变的。

面试题：

1. ```java
   String a = "hello" + "abc"; //创建了几个对象？ -- 1个
   ```

  **分析**：编译器做优化，判断创建的常量池对象是否有引用指向，"hello" + "abc" ==> "helloabc"

2. ```java
    String a = "hello"; 
    String b = "abc"; 
    String c = a + b; //创建了几个对象？ -- 3个

  **分析**：`String c = a + b` 底层执行过程：

  - 先创建一个 StringBuilder sb = StringBuilder();
  - 执行 sb.append(a);
  - sb.append(b);
  - String c = sb.toString();

  最后其实是 c 指向堆中的String对象，该对象的value[]指向常量池中的"helloabc"字符串常量

  **重要规则：常量相加在池中，变量相加在堆中。**

3. 下列程序运行的结果是什么？画出内存布局图？

    ```java
    public class Test {
        String str = new String("hsp");
        final char[] ch = {'j', 'a', 'v', 'a'};
        public void change(String str, char ch[]) {
            str = "java";
            ch[0] = 'h';
        }
        public static void main(String[] args) {
            Test ex = new Test();
            ex.change(ex.str, ex.ch);
            System.out.print(ex.str + "and ");
            System.out.print(ex.ch);
        }
    }

​	输出结果：hsp and hava

<img src="https://gitee.com/dq-agj/imags/raw/master/img/13.3%20%E9%9D%A2%E8%AF%95%E9%A2%98%20%E5%86%85%E5%AD%98%E5%B8%83%E5%B1%80%E5%9B%BE" alt="image-20230108160227776" style="zoom: 50%;" />

### 13.4 String 类的常见方法

- equals ：区分大小写，判断**内容**是否相等
- equalslgnoreCase ：忽略大小写的判断内容是否相等
- length ：获取字符的个数，字符串的长度
- indexOf ：获取字符在字符串中第1次出现的索引，索引从0开始，如果找不到，返回-1
- lastIndexOf ：获取字符在字符串中最后1次出现的索引，索引从0开始，如果找不到，返回-1
- substring ：截取指定范围的子串
  - substring(i) 从索引 i 开始截取后面的内容
  - substring(i, j) 从索引 i 开始截取，直到 索引 j - 1 的位置
- trim ：去前后空格
- charAt ：获取某索引处的字符，注意不能使用 str[index] 这种方式

------

- toUpperCase

- toLowerCase

- concat

  ```java
  String s1 = "宝玉";
  s1 = s1.concat("林黛玉").concat("薛宝钗").concat("together");
  System.out.println(s1);//宝玉林黛玉薛宝钗together
  ```

- replace ：替换字符串中的字符

  ```java
  s1 = "宝玉 and 林黛玉 林黛玉 林黛玉";
  //s1.replace() 方法执行后，返回的结果才是替换过的。注意对 s1 没有任何影响
  String s11 = s1.replace("宝玉", "jack");
  System.out.println(s1);//宝玉 and 林黛玉 林黛玉 林黛玉
  System.out.println(s11);//jack and 林黛玉 林黛玉 林黛玉
  ```

- split ：分割字符串

  ```java
  //1. 以 , 为标准对 poem 进行分割, 返回一个数组
  String poem = "锄禾日当午,汗滴禾下土,谁知盘中餐,粒粒皆辛苦";
  String[] split = poem.split(",");
  //2. 在对字符串进行分割时，如果有特殊字符，需要加入 转义符 \
  poem= "E:\\aaa\\bbb";
  split = poem.split("\\\\");
  
  System.out.println("===分割后内容===");
  for (int i = 0; i < split.length; i++) {
      System.out.println(split[i]);
  }
  ```

- compareTo ：比较两个字符串的大小。前者大返回正数，后者大返回负数，如果相等返回 0

- toCharArray ：转换成字符数组

- format ：格式字符串，%s字符串 %c字符 %d整型 %.2f 浮点型（保留小数点后两位）

  ```java
  String formatStr = "我的姓名是%s 年龄是%d，成绩是%.2f 性别是%c。希望大家喜欢我！";
  String info = String.format(formatStr, name, age, score, gender);
  ```

### 13.5 StringBuffer 类

1. java.lang.StringBuffer 代表可变的字符序列，可以对字符串内容进行增删。
2. StringBuffer 是一个 final 类，不能被继承。
3. 在父类中 AbstractStringBuilder有属性 `char[] value`，不是final，存放的字符串内容在堆中；所有变化（增加、删除）不用每次都更换地址（即不是每次创建新对象），所以效率高于String。

**String StringBuffer StringBuilder 的继承关系**

![image-20230108164550743](https://gitee.com/dq-agj/imags/raw/master/img/String%20StringBuffer%20StringBuilder%20%E7%9A%84%E7%BB%A7%E6%89%BF%E5%85%B3%E7%B3%BB)

**String VS StringBuffer：**

1. String 保存字符串常量，里面的值不能更改，每次String类的更新实际上是更改地址，效率较低。
2. StringBuffer 保存字符串变量，里面的值可以更改，每次更新实际上就是更改内容，不用每次更新地址（只有超出当前内存空间需要重新分配新的内存空间时，才会更新地址），效率较高。

**StringBuffer 构造器**

1. 创建一大小为16的 char[]，用于存放字符内容

   ```java
   StringBuffer stringBuffer = new StringBuffer();
   ```

2. 通过构造器指定 char[] 大小

   ```java
   StringBuffer stringBuffer1 = new StringBuffer(100);
   ```

3. 通过一个String 创建 StringBuffer，char[] 大小就是 str.length() + 16

   ```java
   StringBuffer hello = new StringBuffer("hello");
   ```

**String 和 StringBuffer 相互转换**

```java
// String——>StringBuffer
String str = "hello tom";
//方式1 使用 构造器
StringBuffer stringBuffer = new StringBuffer(str);
//方式2 使用 append 方法
StringBuffer stringBuffer1 = new StringBuffer();
stringBuffer1 = stringBuffer1.append(str);

// StringBuffer -> String
StringBuffer stringBuffer3 = new StringBuffer("韩顺平教育");
//方式1 使用 StringBuffer 提供的 toString 方法
String s = stringBuffer3.toString();
//方式2: 使用 构造器
String s1 = new String(stringBufferf3);
```

**StringBuffer 类常见方法**

- append：尾插
- delete(start, end)：删除索引为 >=start && <end 处的字符
- replace(start, end, str)：使用 字符串str 替换 索引 [start, end) 的内容
- indexOf：获取指定子串在字符串中第1次出现的索引，如果找不到则返回-1
- insert(i, str)：在索引为 i 的位置插入 字符串str
- length：长度

**测试题**

```java
public class StringBufferExercise01 {
    public static void main(String[] args) {
        String str = null;
        StringBuffer sb = new StringBuffer();
        sb.append(str);//需要看源码 , 底层调用的是 AbstractStringBuilder 的 appendNull
        System.out.println(sb.length());//4

        System.out.println(sb);//null
        //下面的构造器，会抛出NullpointerException
        StringBuffer sb1 = new StringBuffer(str);//看底层源码 super(str.length() + 16);
        System.out.println(sb1);
    }
}
```

### 13.6 StringBuilder 类

一个可变的字符序列。此类提供一个与StringBuffer 兼容的API，但不保证同步（StringBuilder 不是线程安全）。该类被设计用作 StringBuffer的一个简易替换，**用在字符串缓冲区被单个线程使用的时候**。如果可能，建议优先采用该类因为在大多数实现中，它比 StringBuffer要快。

**String、StringBuffer 和 StringBuilder 的比较与选择**

| 类            |                                                              |
| ------------- | ------------------------------------------------------------ |
| String        | 不可变字符序列、效率低、复用率高（字符串内容存放在池中，可以被多次引用） |
| StringBuffer  | 可变字符序列、效率较高（增删）、线程安全                     |
| StringBuilder | 可变字符序列、效率最高、线程不安全                           |

String使用注意说明：如果对字符串做大量修改，不要使用String

```java
string s = "a"; //创建了一个字符串
s += "b"; //实际上原来的"a"字符串对象已经丢弃了，现在又产生了一个字符串s+"b”(也就是"ab")。如果多次执行这些改变串内容的操作，会导致大量副本字符串对象存留在内存中，降低效率，极大影响程序的性能
```

- 如果字符串存在大量的修改操作，并在单线程的情况，使用 StringBuilder
- 如果字符串存在大量的修改操作，并在多线程的情况，使用 StringBuffer
- 如果我们字符串很少修改（比如配置信息等），被多个对象引用，使用String

### 13.7 Math 类

Math 类包含用于执行基本数学运算的静态方法，如初等指数、对数、平方根和三角函数。

### 13.8 Arrays 类

Arrays 里面包含了一系列静态方法，用于管理或操作数组（比如排序和搜索）。

1. toString 返回数组的字符串形式

   ```java
   Arrays.toString(arr)
   ```

2. sort 排序（自然排序和定制排序）

   ```java
   // 默认排序方法
   Arrays.sort(arr);
   
   // 定制排序：传入两个参数 
   // (1) 排序的数组 arr；(2) 实现了Comparator接口的匿名内部类 , 要求实现 compare 方法
   Arrays.sort(arr, new Comparator<Integer>() {
       @Override
       public int compare(Integer o1, Integer o2) {
           return o2 - o1;
       }
   });
   ```

3. binarySearch 通过二分搜索法进行查找，要求必须排好序；如果数组中不存在该元素，就返回 -(low + 1)

   ```java
   int index = Arrays.binarySearch(arr, 3);
   ```

4. copyOf 数组元素的复制

   ```java
   //1. 从 arr 数组中，拷贝 arr.length个元素到 newArr数组中
   Integer[] newArr = Arrays.copyOf(arr, arr.length);
   //2. 如果拷贝的长度 > arr.length 就在新数组的后面 增加 null
   //3. 如果拷贝长度 < 0 就抛出异常NegativeArraySizeException
   //4. 该方法的底层使用的是 System.arraycopy()
   ```

5. fill 数组元素的填充

   ```java
   Integer num = new Integer[] {9, 3, 2};
   Arrays.fill(num, 99);
   ```

6. equals 比较两个数组元素内容是否完全一致

   ```java
   boolean equals = Arrays.equals(arr, arr2);
   ```

7. asList 将一组值转换成 list

   ```java
   List<Integer> asList = Arrays.asList(2, 3, 4, 5, 6, 1);
   System.out.println("asList=" + asList); //[2, 3, 4, 5, 6, 1]
   System.out.println("asList的运行类型" + asList.getClass()); 
   //编译类型 List(接口)
   //运行类型 class java.util.Arrays$ArrayList，是Arrays类的静态内部类
   ```

### 13.9 System 类

- exit ：退出当前程序
- arraycopy ：复制数组元素，适合底层调用
- currentTimeMillens ：返回当前时间距离 1970-1-1 的毫秒数
- gc ：运行垃圾回收机制

### 13.10 BigInteger 和 BigDecimal 类

应用场景：BigInteger 适合保存比较大的整型；BigDecimal适合保存精度更高的浮点型

常见方法：add 加；subtract 减；multiply 乘；divide 除

注意：在调用 BigDecimal 的 divide 方法时，可能因为除不尽抛出异常 ArithmeticException，这时指定精度即可。`bigDecimal.divide(bigDecimal2, BigDecimal.ROUND_CEILING)`，如果有无限循环小数，就会保留 分子（被除数） 的精度。

### 13.11 日期类

#### 13.11.1 第一代日期

Date：精确到毫秒，代表特定的瞬间。

SimpleDateFormat：格式和解析日期的类。它允许进行格式化（日期->文本）、解析（文本->日期）、规范化。

```java
public class Date01 {
    public static void main(String[] args) throws ParseException {
        // 获取当前系统时间； 这里的 Date 类是在java.util包
        Date d1 = new Date(); //获取当前系统时间
        System.out.println("当前日期=" + d1);
        Date d2 = new Date(9234567); //通过指定毫秒数得到时间
        System.out.println("d2=" + d2);

        // 创建 SimpleDateFormat对象，可以指定相应的格式
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 hh:mm:ss E");
        String format = sdf.format(d1); // format:将日期转换成指定格式的字符串
        System.out.println("当前日期=" + format);

        // String -> Date， 使用的 sdf 格式需要和给的String的格式一样，否则会抛出转换异常
        String s = "1996年01月01日 10:20:30 星期一";
        Date parse = sdf.parse(s);
        System.out.println("parse=" + sdf.format(parse));
    }
}
```

#### 13.11.2 第二代日期

Calendar：抽象类，为特定瞬间与一组日历字段（YEAR, MONTH, DAY_OF_MONTH, HOUR等）之间的转换以及操作这些日历字段提供了一些方法。

```java
public class Calendar_ {
    public static void main(String[] args) {
        // Calendar是一个抽象类， 并且构造器是 protected，可以通过 getInstance() 来获取实例
        Calendar c = Calendar.getInstance(); //创建日历类对象
        System.out.println("c=" + c);
        // 获取日历对象的某个日历字段
        System.out.println("年：" + c.get(Calendar.YEAR));
        System.out.println("月：" + (c.get(Calendar.MONTH) + 1));// Calendar 返回月，是按照 0 开始编号
        System.out.println("日：" + c.get(Calendar.DAY_OF_MONTH));
        System.out.println("小时：" + c.get(Calendar.HOUR));// 12小时制
        System.out.println("小时：" + c.get(Calendar.HOUR_OF_DAY));// 24小时制
        System.out.println("分钟：" + c.get(Calendar.MINUTE));
        System.out.println("秒：" + c.get(Calendar.SECOND));
        //Calender 没有专门的格式化方法，所以需要程序员自己来组合显示
        System.out.println(c.get(Calendar.YEAR) + "-" + (c.get(Calendar.MONTH) + 1) + "-" + c.get(Calendar.DAY_OF_MONTH) + " " + c.get(Calendar.HOUR_OF_DAY) + ":" + c.get(Calendar.MINUTE) + ":" + c.get(Calendar.SECOND) );
    }
}
```

#### 13.11.3 第三代日期

前面两代日期类的不足分析：

JDK 1.0中包含了一个java.util.Date类，但是它的大多数方法已经在JDK 1.1引入Calendar类之后被弃用了。而Calendar也存在问题。

1. 可变性：像日期和时间这样的类应该是不可变的。
2. 偏移性：Date年份是从1970开始的，而Calendar月份都从0开始。
3. 格式化：格式化只对Date有用，Calendar则不行。
4. 此外，它们也都不是线程安全的；不能处理闰秒等（每隔2天，多出1s）。

JDK8加入：

- LocalDate（日期/年月日）：只包含日期，可以获取日期字段
- LocalTime（时间/时分秒）：只包含时间，可以获取时间字段
- LocalDateTime（日期时间/年月日时分秒）：包含日期+时间，可以获取日期和时间字段

```java
public class LocalDate_ {
    public static void main(String[] args) {
        //1. 使用静态方法 now() 返回表示当前日期时间的对象
        LocalDateTime ldt = LocalDateTime.now(); //LocalDate.now();//LocalTime.now()
        System.out.println(ldt); //2023-01-10T16:36:38.600

        //2. 使用 DateTimeFormatter 对象来进行格式化（各个格式参数参看jdk8文档）
        DateTimeFormatter dtf = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        String format = dtf.format(ldt);
        System.out.println("格式化的日期=" + format);//2023-01-10 16:36:38

        System.out.println("年=" + ldt.getYear());
        System.out.println("月=" + ldt.getMonth());//JANUARY
        System.out.println("月=" + ldt.getMonthValue());//1
        System.out.println("日=" + ldt.getDayOfMonth());
        System.out.println("时=" + ldt.getHour());
        System.out.println("分=" + ldt.getMinute());
        System.out.println("秒=" + ldt.getSecond());

        //提供 plus 和 minus方法可以对当前时间进行加或者减
        LocalDateTime ldt1 = ldt.plusDays(890);
        System.out.println("890天后=" + dtf.format(ldt1));
        LocalDateTime ldt2 = ldt.minusMinutes(3456);
        System.out.println("3456分钟前 日期=" + dtf.format(ldt2));
    }
}
```

**Instant 时间戳**

类似于Date；提供了一系列和Date类转换的方式

```java
public class Instant_ {
    public static void main(String[] args) {
        //1.通过 静态方法 now() 获取表示当前时间戳的对象
        Instant now = Instant.now();
        System.out.println(now);//2023-01-10T08:44:09.934Z
        //2. Instant 转成 Date
        Date date = Date.from(now);
        //3. Date 转成 Instant
        Instant instant = date.toInstant();
    }
}
```



## 第 14 章 集合

### 14.1 集合的理解

前面我们保存多个数据使用的是数组，那么数组有不足的地方：

1. 长度开始时必须指定，而且一旦指定，不能更改
2. 保存的必须为同一类型的元素
3. 使用数组进行增加/删除元素比较麻烦

集合：

1. 可以动态保存任意多个对象，使用比较方便
2. 提供了一系列方便的操作对象的方法：add、remove、 set、get等，添加、删除新元素的代码简洁明了

### 14.2 集合的框架体系

Java 的集合类很多，主要分为两大类：

**Collection**：Collection 接口有两个重要的子接口 List 和 Set，他们的实现子类都是单列集合

<img src="https://gitee.com/dq-agj/imags/raw/master/img/%E9%9B%86%E5%90%88%E7%9A%84%E6%A1%86%E6%9E%B6%E4%BD%93%E7%B3%BBCollection" alt="image-20230110174825566"  />

**Map**：Map 接口的实现子类是双列集合，存放 K-V（键值对）

<img src="https://gitee.com/dq-agj/imags/raw/master/img/%E9%9B%86%E5%90%88%E7%9A%84%E6%A1%86%E6%9E%B6%E4%BD%93%E7%B3%BBMap" alt="image-20230110174855457" style="zoom: 50%;" />

### 14.3 Collection 接口和常用方法

**Collection 接口的常用方法**

```java
// 说明：以ArrayList实现类来演示 Collection 常用方法
public class CollectionMethod {
    @SuppressWarnings({"all"})
    public static void main(String[] args) {
        List list = new ArrayList();
// add:添加单个元素
        list.add("jack");
        list.add(10);//list.add(new Integer(10))
        list.add(true);
        System.out.println("list=" + list);
// remove:删除指定元素
        //list.remove(0);//删除第一个元素
        list.remove(true);//指定删除某个元素
        System.out.println("list=" + list);
// contains:查找元素是否存在
        System.out.println(list.contains("jack"));//T
// size:获取元素个数
        System.out.println(list.size());//2
// isEmpty:判断是否为空
        System.out.println(list.isEmpty());//F
// clear:清空
        list.clear();
        System.out.println("list=" + list);
// addAll:添加多个元素
        ArrayList list2 = new ArrayList();
        list2.add("红楼梦");
        list2.add("三国演义");
        list.addAll(list2);
        System.out.println("list=" + list);
// containsAll:查找多个元素是否都存在
        System.out.println(list.containsAll(list2));//T
// removeAll：删除多个元素
        list.add("聊斋");
        list.removeAll(list2);
        System.out.println("list=" + list);//[聊斋]
    }
}
```

**Collection 接口遍历元素方式 1 - 使用 Iterator（迭代器）**

lterator 对象称为迭代器，主要用于遍历 Collection 集合中的元素。

所有实现了 Collection 接口的集合类都有一个 iterator() 方法，用以返回一个实现了 iterator 接口的对象（即一个迭代器）。

![image-20230121004606065](https://gitee.com/dq-agj/imags/raw/master/img/lterator%E7%9A%84%E7%BB%93%E6%9E%84)

```java
//1. 先得到 col 对应的 迭代器
Iterator iterator = col.iterator();
//2. 使用 while 循环遍历(快捷键快速生成 => itit)
while (iterator.hasNext()) { //判断是否还有数据
    Object obj = iterator.next();// 返回下一个元素，类型是Object
    System.out.println("obj=" + obj);
}
//3. 当退出while循环后 , 这时iterator迭代器，指向最后的元素
//提示：在调用iterator.next()方法之前必须要调用iterator.hasNext()进行检测。若不调用，且下一条记录无效，直接调用iterator.next()会抛出 NoSuchElementException 异常。
//4. 如果希望再次遍历，需要重置我们的迭代器
```

**Collection 接口遍历对象方式 2 - for 循环增强**

```java
// 增强for，底层仍然是迭代器，可以理解成就是简化版本的迭代器遍历（快捷键方式 I）
for (Object book : col) {
    System.out.println("book=" + book);
}
```

### 14.4 List 接口和常用方法

**List 接口基本介绍**

1. List 集合类中元素**有序**（即添加顺序和取出顺序一致）、且**可重复**；
2. ist集合中的每个元素都有其对应的顺序索引，即支持索引。eg：`list.get(0)`

**List 接口的常用方法**

```java
public class ListMethod {
    @SuppressWarnings({"all"})
    public static void main(String[] args) {
        List list = new ArrayList();
        list.add("张三丰");
        list.add("贾宝玉");
        
// void add(int index, Object ele):在index位置插入ele元素
        list.add(1, "韩顺平");
        System.out.println("list=" + list);
// boolean addAll(int index, Collection eles):从index位置开始将eles中的所有元素添加进来
        List list2 = new ArrayList();
        list2.add("jack");
        list2.add("tom");
        list.addAll(1, list2);
        System.out.println("list=" + list);
// Object get(int index):获取指定index位置的元素
        System.out.println(list.get(3));//韩顺平
// int indexOf(Object obj):返回obj在集合中首次出现的位置
        System.out.println(list.indexOf("tom"));//2
// int lastIndexOf(Object obj):返回obj在当前集合中末次出现的位置
        list.add("韩顺平");
        System.out.println("list=" + list);
        System.out.println(list.lastIndexOf("韩顺平"));
// Object remove(int index):移除指定index位置的元素，并返回此元素
        list.remove(0);
        System.out.println("list=" + list);
// Object set(int index, Object ele):设置指定index位置的元素为ele, 相当于是替换.
        list.set(1, "玛丽");
        System.out.println("list=" + list);
// List subList(int fromIndex, int toIndex):返回从fromIndex到toIndex位置的子集合（fromIndex <= subList < toIndex）
        List returnlist = list.subList(0, 2);
        System.out.println("returnlist=" + returnlist);
    }
}
```

**List 接口的三种遍历方式**

```java
//1. 迭代器
Iterator iterator = list.iterator();
while (iterator.hasNext()) {
    Object obj =  iterator.next();
    System.out.println(obj);
}
//2. 增强for
for (Object o : list) {
    System.out.println("o=" + o);
}
//3. 使用普通for
for (int i = 0; i < list.size(); i++) {
    System.out.println("对象=" + list.get(i));
}
```

### 14.5 List 接口实现类 - ArrayList

- ArrayList 可以加入多个null
- ArrayList 是由**数组**来实现数据存储的

**ArrayList 的底层操作机制**（扩容机制）

1. ArrayList中维护了一个 Object 类型的数组 elementData。

   ```java
   transient Object[] elementData; //transient表示瞬间，短暂的，表示该属性不会被序列化
   ```

2. 当创建 ArrayList 对象时，如果使用的是无参构造器，则初始 elementData 容量为0；第1次添加则扩容elementData 为10，如需要再次扩容，则扩容elementData为1.5倍。

3. 如果使用的是指定大小的构造器，则初始elementData容量为指定大小；如果需要扩容，则直接扩容elementData 为1.5倍。

### 14.6 List 接口实现类 - Vector

Vector 底层也是一个对象数组。

```java
protected Object[] elementData;
```

Vector 是线程同步的，即**线程安全**，Vector 类的操作方法带有 synchronized。

**Vector 和 ArrayList 的比较**

|           | 底层结构 | 线程安全，效率 | 扩容机制                                                     |
| --------- | -------- | -------------- | ------------------------------------------------------------ |
| ArrayList | 可变数组 | 不安全，效率高 | 如果是无参，默认初始大小为0<br/>1.第一次扩容到10<br/>2.从第二次开始按1.5倍扩容<br/> 如果有参构造（指定大小），每次直接按1.5倍扩容。 |
| Vector    | 可变数组 | 安全，效率不高 | 如果是无参，默认初始大小为10，满后按2倍扩容<br/>如果有参构造（指定大小），每次直接按2倍扩容。 |

ArrayList 基本等同于 Vector，除了 ArrayList 是线程不安全（但执行效率高）。在多线程情况下，不建议使用ArrayList。

### 14.7 List 接口实现类 - LinkedList

- LinkedList 底层实现了双向**链表**和双端**队列**特点
- 可以添加任意元素（元素可以重复），包括null
- 线程不安全，没有实现同步

**LinkedList 的底层操作机制**：LinkedList底层维护了一个双向链表：两个属性 first 和 last 分别指向首节点和尾节点，每个节点（Node对象）里面维护了prev、next、item三个属性。所以LinkedList的元素的添加和删除，不是通过数组完成的，相对来说效率较高。

**LinkedList 的增删改查案例**：

```java
public class LinkedListCRUD {
    public static void main(String[] args) {
        LinkedList linkedList = new LinkedList();
        //添加节点
        linkedList.add(1);
        linkedList.add(2);
        linkedList.add(3);
        System.out.println("linkedList=" + linkedList);

        //删除结点
        linkedList.remove(); // 这里默认删除的是第一个结点
        //linkedList.remove(2);
        System.out.println("linkedList=" + linkedList);

        //修改某个结点对象
        linkedList.set(1, 999);
        System.out.println("linkedList=" + linkedList);

        //得到某个结点对象
        Object o = linkedList.get(1);
        System.out.println(o);//999
    }
}
```

**ArrayList 和 LinkedList 比较**

|            | 底层结构 | 增删效率           | 改查效率 |
| ---------- | -------- | ------------------ | -------- |
| ArrayList  | 可变数组 | 较低，数组扩容     | 较高     |
| LinkedList | 双向链表 | 较高，通过链表追加 | 较低     |

### 14.9 Set 接口和常用方法

**Set 接口基本介绍**

1. 无序（添加和取出的顺序不一致），没有索引
2. 不允许重复元素，所以最多包含一个null

**Set 接口的常用方法**

和 List 接口一样, Set 接口也是 Collection 的子接口，因此，常用方法和 Collection 接口一样。

**Set 接口的遍历方式**

1. 可以使用迭代器
2. 增强for
3. **不能使用**索引的方式来获取

### 14.10 Set 接口实现类 - HashSet

```java
public HashSet() {
    map = new HashMap<>();
}
```

HashSet 底层是 HashMap， HashMap底层是 数组+链表+红黑树

添加一个元素时：

1. 先获取元素的哈希值（hashCode方法）。

2. 对哈希值进行运算，得出一个索引值即为要存放在哈希表中的位置号。

3. 如果该位置上没有其他元素，则直接存放；

   否则，进行equals判断，如果相等则不再添加，如果不相等则以链表的方式追加。

在 Java8 中，如果一条链表的元素个数到达 TREEIFY_THRESHOLD（默认是8），并且 table 的大小 >= MIN _TREEIFY_CAPACIT（(默认64），就会进行树化（红黑树）



### 14.11 Set 接口实现类 - LinkedHashSet







[TOC]

