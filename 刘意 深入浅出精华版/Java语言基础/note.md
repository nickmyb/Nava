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
