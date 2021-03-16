Java语言基础
============

## 1. JDK安装

- [OpenJDK](https://openjdk.java.net/)
- [JDK Download](https://jdk.java.net/)

## 2. idea

### 2.1 创建新项目

1. New Project
2. Empty Project -> Next
3. Project name: Demo, Project location: ~/Codes/Demo -> Finish
4. Project Settings -> Modules -> + -> New Module -> Java -> Module SDK -> JDK INSTALLED PATH -> Next -> Module name: HelloWorld -> Finish -> OK
5. src -> New -> Package -> com.nickmyb -> New -> Java Class -> HelloWorld

### 2.2 快捷键

1. 内容提示: Ctrl + Alt + Spac
1. 注释: Ctrl [+ Shift] + /
2. 格式化: Ctrl + Alt + L

## 3. Java基础

1. 源代码为ClassName.java -> ClassName.java中public类名需要和文件名保持一致
2. 编译: javac ClassName.java
3. 运行: java ClassName

## 4. Java基础语法

- 关键字
    - 全部都是小写
- 标识符
    - 大小写字母/数字/$_
    - 不能以数字开头且不能是关键字
    - 命名规则: 见名知意
        - 包: 就是文件夹，用于区分相同类名，全部小写
        - 类和接口: 每个单词首字母大写
        - 方法和变量: 驼峰
        - 常量: 每个字母都大写，_分隔
- 注释
    - //
    - /* */
    - 文档注释
    - 需求 -> 分析 -> 实现
- 常量
    - "" / ''
    - 0b / 0 / 0x
- 变量
    - 数据类型 标识符 = 初始化
    - 使用前必须先初始化
- 进制
    - 计算机中运算都是以补码进行
- 数据类型
    - 基本数据类型
        - byte / short / int / long(L)
        - char
        - float(F) / double
        - boolean
        - 自动类型转换：byte / short / char -> int -> long -> float -> double
        - 常量由于编译器优化先计算结果，变量先类型提升
        - 'a' = 97, 'A' = 65, '0' = 48
- 重载
    - 同名方法，参数个数或者参数类型不同
- 数组
    - 存储同一种数据类型的多个元素的容器
    - int[] a = new int[3]
    - int[] a = new int[] {1, 2, 3} / int[] a = {1, 2, 3}
    - array.length
    - int[][] a = new int[3][4] / int[][] a = new int[3][] / int[][] a = {{}, {}, {}}
- 栈
    - 局部变量
- 堆
    - new, 有默认值

## 5. 面向对象

类：一组相关属性和行为的集合，类是事物转化来的，成员变量用于描述事物的属性，变量的范围越小越好

类（名词） -> 类的功能 -> 类与类的关系

- 封装
    - private: 只能在本类中访问
    - 成员变量用private修饰,并且提供get&set方法
    - 避免对成员变量的不合法的直接操作
- this：局部变量隐藏成员变量
- 构造函数
    - 方法名和类名相同且没有返回值类型
    - 默认初始化 -> 显式初始化 -> 构造函数
- toString(): "" + this会导致无限递归
- import：必须在所有class的前面
- static
    - 随着类加载而加载，优先于对象存在
    - 所有对象共享
    - 可以通过类名调用，也可以通过对象调用
    - 类成员 / 对象成员
    - 堆 / 栈 / 方法区(class内容(成员变量/成员方法) / 静态区 / 类方法区 )
    - static方法只能访问static相关内容，this此时还不存在
- 文档注释
    - javadoc -d dir -author -version xxx.java
- 文档
    - https://docs.oracle.com/javase/8/docs/api/
- 代码块
- 继承
    - 子类不能继承父类的private属性和方法
    - 子类不继承父类的构造方法，但可以通过super访问父类的构造方法
    - 继承打破封装，子类也可以修改父类的内容
    - 不要为了部分功能而去继承
    - Son "is a" Father
    - 子类所有构造方法都会默认第一条调用父类的无参构造方法: super(),所以super(...)/this(...)需要在构造方法的第一条
    - static {} / {} / 构造函数{}
    - 分层初始化而不是先调用super(),先初始化父类数据后初始化子类数据
    - 重写: 返回值 方法名 参数 完全相同 权限>= 最好一模一样
- final
    - final修饰class，这个class无法被继承
    - final修饰方法，这个方法不能被重写
    - final修饰变量，即常量，成员变量要在自己构造方法结束前有且仅有被赋值一次，static成员变量要在static构造结束前有且仅有被赋值一次，局部变量使用前有且仅有被赋值一次
- 多态
    - 继承
    - 方法重写
    - 父类引用指向子类对象
    - 成员变量: 编译看左边，运行看左边（变量没有重写）
    - 构造方法
    - 成员方法: 编译看左边，运行看右边
    - 静态方法: 编译看左边，运行看左边，类相关算不算重写
    - 不能使用子类的特有方法，使用需要先强转
    - 属性是外在表现，方法是内在表现
- 抽象类
    - 抽象类和抽象方法abstract修饰
    - 抽象方法不能有方法体
    - 有抽象方法一定要声明为抽象类
    - 子类要么重写所有abstract方法要么声明抽象类
    - Java中父类的属性感觉一定要通过父类的方法访问
    - abstract冲突组合：private无法被继承 / final无法被重写 / static属于类可直接调用但方法体为空
- 分析和实现
    - 分析：具体到抽象
    - 实现：抽象到具体
- 接口
    - 接口中的成员变量默认是 public static final
    - 接口没有构造方法
    - 接口成员方法默认是抽象方法, public abstract,只能是抽象方法
    - 接口与接口可以多继承(类是单继承)
    - "like a"
- 包
    - 分类管理(先模块后功能)
    - 相同包路径下不能有重名包
    - package必须是第一条可执行代码
    - javac -d . xxx.java -> java p1.p2.xxx
    - 不同包下访问要加包的全路径
    - 类名不存在 -> a.b.c未编译 -> 类访问权限
    - import a.b.ClassName
- 修饰符: private default protected public
    - 方法:
        - 本类 本包 不同包子类 不同包非子类
    - 类:
        - 不能使用private protected static
    - 构造方法:
        - 不能使用static final abstract
- 内部类
    - 内部类可以直接访问外部类的成员
    - 外部类访问内部类必须通过对象
    - 成员内部类
        - 访问内部类成员
            - non-static: OuterClass.InnerClass oi = new OuterClass().new InnerClass();
            - static: OuterClass.InnerClass oi = new OuterClass.InnerClass();
        - 但内部类一般用private修饰不给在外部访问
        - static内部类只能访问外部类的static成员,static内部类的方法仍然可以为非static方法,static内部类不能用外部类对象访问
    - 内部类和外部类没有继承关系
    - 局部内部类
        - 访问内部类成员
        - 局部内部类方法中访问的局部变量必须为final(局部变量调用后就回收,对象需要垃圾回收,所以需要final,Java8后自动final)
    - 匿名内部类
        - new ClassName/InterfaceName() { overwrite method }

## 5. Java常见API

- Object
    - hashCode
    - getClass
    - toString
    - equals
    - finalize
    - clone
- Scanner
- String
- StringBuffer & StringBuilder
- Arrays
- Boxing
