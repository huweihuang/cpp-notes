[TOC]

# 1. 简介

C++ 是一种静态类型的、编译式的、通用的、大小写敏感的、不规则的编程语言，支持过程化编程、面向对象编程和泛型编程。

## 1.1. 特点

C++ 完全支持面向对象的程序设计，包括面向对象开发的四大特性：

- 封装
- 抽象
- 继承
- 多态

# 2. 基本语法

C++ 程序可以定义为对象的集合，这些对象通过调用彼此的方法进行交互。

- **对象 -** 对象具有状态和行为。例如：一只狗的状态 - 颜色、名称、品种，行为 - 摇动、叫唤、吃。对象是类的实例。
- **类 -** 类可以定义为描述对象行为/状态的模板/蓝图。
- **方法 -** 从基本上说，一个方法表示一种行为。一个类可以包含多个方法。可以在方法中写入逻辑、操作数据以及执行所有的动作。
- **即时变量 -** 每个对象都有其独特的即时变量。对象的状态是由这些即时变量的值创建的。

## 2.1. 程序结构

```c
#include <iostream>            // 头文件
using namespace std;           // 告诉编译器使用 std 命名空间

int main()                     // main() 是程序开始执行的地方
{
   cout << "Hello World";      // 输出 Hello World
   return 0;                   // 终止函数，返回0
}                              // 分号表示语句结束，不以换行为结束，大括号{}表示语句块
```

## 2.2. main入口函数

main() 函数是 C++ 程序的入口函数，C++ 标准规定 main() 函数的返回值类型为 int，返回值用于表示程序的退出状态，返回 0 表示程序正常退出，返回非 0，表示出现异常。C++ 标准规定，main() 函数原型有两种：

```cpp
//第一种
int main();

//第二种
int main(int argc，char* argv[]);
int main(int argc，char** argv);
```

## 2.3. 编译和执行

```bash
$ g++ hello.cpp
$ ./a.out
Hello World
```

## 2.4. 标准输入输出

iostream标准库，提供IO相关的操作，包括：

- 标准输入：cin

- 标准输出：cout

- 标准错误：cerr

- 一般日志：clog

示例：

```cpp
# include <iostream>

int main()
{
    std::cout << "enter two number" << std::endl;
    int v1=0, v2 = 0;
    std::cin >> v1 >> v2;
    std::cout << "the sum of" << v1 << "and" << v2 
              << "is" << v1+v2 << std::endl;
    return 0;
}
```

## 2.5. 注释

**单行注释**

```c
// 这是单行注释
```

**多行注释**

```c
/* 这是注释 */

/* C++ 注释也可以
 * 跨行
 */
```

## 2.6. 标识符

- C++ 标识符是用来标识变量、函数、类、模块，或任何其他用户自定义项目的名称。
- 一个标识符以字母 A-Z 或 a-z 或下划线 _ 开始，后跟零个或多个字母、下划线和数字（0-9）。
- C++ 标识符内不允许出现标点字符，比如 @、& 和 %。C++ 是区分大小写的编程语言。

# 3. 关键字

| asm          | else      | new              | this     |
| ------------ | --------- | ---------------- | -------- |
| auto         | enum      | operator         | throw    |
| bool         | explicit  | private          | true     |
| break        | export    | protected        | try      |
| case         | extern    | public           | typedef  |
| catch        | false     | register         | typeid   |
| char         | float     | reinterpret_cast | typename |
| class        | for       | return           | union    |
| const        | friend    | short            | unsigned |
| const_cast   | goto      | signed           | using    |
| continue     | if        | sizeof           | virtual  |
| default      | inline    | static           | void     |
| delete       | int       | static_cast      | volatile |
| do           | long      | struct           | wchar_t  |
| double       | mutable   | switch           | while    |
| dynamic_cast | namespace | template         | -        |

完整关键字介绍可查阅：[C++ 的关键字（保留字）完整介绍](https://www.runoob.com/w3cnote/cpp-keyword-intro.html)

# 4. 头文件

C++程序中通常包含两类文件，`.cpp`文件为c++的源文件，`.h`文件为c++的头文件。

头文件用来存储需要被调用的类、变量及函数声明（仅包含入参出参，不包含函数实现定义）。

通过`#include`将头文件的内容给源文件引用。

例子：

math.cpp

```cpp
/* math.cpp */
double f1()
{
    //do something here....
    return;
}
double f2(double a)
{
    //do something here...
    return a * a;
}
/* end of math.cpp */
```

头文件math.h

```cpp
/* math.h */
double f1();
double f2(double);
/* end of math.h */
```

源文件main.cpp

```cpp
/* main.cpp */
#include "math.h"   // 引入头文件
main()
{
    int number1 = f1();
    int number2 = f2(number1);
}
/* end of main.cpp */
```

# 5. C++谷歌代码规范

具体参考：[Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)

参考：

- https://www.tutorialspoint.com/cplusplus/index.htm
- https://www.runoob.com/cplusplus/cpp-tutorial.html
- [理解 C++ 中的头文件和源文件的作用 | 菜鸟教程](https://www.runoob.com/w3cnote/cpp-header.html)