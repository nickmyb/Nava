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

1. 源代码为ClassName.java -> ClassName.java中类名建议保持一致
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
