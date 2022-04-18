# 数据类型

# 1. 变量

## 1.1. 变量定义

### 1.1.1. 变量声明

```c
<type> <variable_list>;
```

- type：表示声明变量的数据类型。
- variable_list：表示变量的名字，可以多个，以逗号分隔，分号结束。

变量命名规范：

- 变量名一般使用小写

- 用户自定义的类用一般用大写字母开头

- 多个单词用下划线或驼峰格式

例如：

```c
int    i, j, k;
char   c, ch;
float  f, salary;
double d;
```

### 1.1.2. 声明并初始化

```c
<type> <variable_name> = <value>;
```

例如：

```c
extern int d = 3, f = 5;    // d 和 f 的声明 
int d = 3, f = 5;           // 定义并初始化 d 和 f
byte z = 22;                // 定义并初始化 z
char x = 'x';               // 变量 x 的值为 'x'
```

### 1.1.3. 变量的作用域

变量的作用域大多用花括号分隔，建议当你第一次使用变量的时候再定义它。

- 全局变量：所有花括号之外

- 局部变量：花括号之内

- 嵌套作用域：内部同名变量会覆盖外部同名变量

## 1.2. 变量类型

| 类型   | 关键字     | 其他类型                             |
|:---- |:------- | -------------------------------- |
| 布尔型  | bool    |                                  |
| 字符型  | char    |                                  |
| 整型   | int     | short 短整型，long 长整型，long long 长整型 |
| 浮点型  | float   |                                  |
| 双浮点型 | double  | long double拓展精度浮点数               |
| 空类型  | void    |                                  |
| 宽字符型 | wchar_t |                                  |

### 1.2.1. 整型

使用int执行整数运算。如果超过int的范围，则使用long long类型。

### 1.2.2. 浮点型

单精度float，32bit表示，双精度double，64bit表示。浮点运算选择double类型，因为float会精度不够，而单精度和双精度计算代价相差无几。

### 1.2.3. 布尔型

### 1.2.4. 字符型

## 1.3. 变量作用域

### 1.3.1. 全局变量

`全局变量`：函数外定义的变量。全局变量表示整个程序都可以使用的变量。

### 1.3.2. 局部变量

`局部变量`：函数内定义的变量。函数内同名的局部变量会覆盖全局变量。

# 2. 常量

## 2.1. 定义常量

> 常量名字一般定义为全大写单词

- 使用 **#define** 预处理器。

```c
// define格式
#define identifier value

// 例如
#define LENGTH 10   
#define WIDTH  5
#define NEWLINE '\n'
```

- 使用 **const** 关键字。

```c
// const格式
const type variable = value;

// 例如
#include <iostream>
using namespace std;

int main()
{
   const int  LENGTH = 10;
   const int  WIDTH  = 5;
   const char NEWLINE = '\n';
   int area;  

   area = LENGTH * WIDTH;
   cout << area;
   cout << NEWLINE;
   return 0;
}
```

# 3. 复合类型

## 3.0. 命名空间的using声明

使用到的库函数一般属于某个命名空间下，例如`std::cin`属于命名空间`std`，通过作用域操作符`::`来引用。也可以使用`using`声明，则调用时无需添加前缀。

```cpp
using namespace::name;
```

**每个名字都需要独立的using声明**

```cpp
using std::cin;
using std::cout;
using std::endl;

int main(){
    cout << "enter two number" << endl;
    int v1,v2;
    cin >> v1 >> v2;
}
```

**头文件不包含using声明**

头文件一般不使用using声明，避免名字冲突。

## 3.1. 数组

数据的大小是固定的，不能无限向数据添加元素。

## 3.2. 字符串string

## 3.3. 向量Vector

标准库类型vector表示对象的集合，其中对象的类型都相同。

使用vector，先做声明：

```cpp
#include <vector>;
using std::vector;
```

## 3.3. 指针

**指针的定义**

指针是指向另一种类型的复合类型，本身是一个对象，可以被赋值和拷贝。指针无需在定义时赋值。通过`*`来定义指针。

```cpp
int *p1, *p2; // p1，p2都是指向int类型的指针
```

**获取对象的地址**

指针存放某个对象的地址，使用取地址符（&）获取该地址。

```cpp
int ival=42;
int *p=&ival; // p存放 ival的地址
```

**指针的值**

指针的值（即地址）应属于下列四种状态之一：

- 指向某个对象

- 指定紧邻对象所占空间的下一个位置

- 空指针，没有指向任何对象

- 无效指针，即上述情况之外

**空指针**

空指针不指向任何对象，在使用指针之前应检查该指针是否为空，生成空指针的方式有：

```cpp
int *p1=nullptr; // c++11新引入的方式，建议使用该方式
int *p2=0;
int *p3=NULL;
```

建议初始化所有指针，避免访问空指针导致程序崩溃。

**赋值和指针**

给指针赋值就是令他存放一个新的地址，指向一个新的对象。

**指针的指针**

指针也有内存地址，因此指针的指针表示指针的内存地址。

## 3.4. 引用

引用为对象起了另外的名字，通过`&d`的格式来定义引用类型。引用并非对象，而是对象的别名。

```cpp
int ival = 1024;
int &refVal = ival; // refVal是ival另外的名字
```

## 3.5. 结构体(struct)

```cpp
struct Sales_data{
    std::string bookNo;
    unsigned units_sold=0;
    double revenue =0.0;
}; 
```

# 4. 特殊类型

参考：

- https://www.tutorialspoint.com/cplusplus/index.htm
- https://www.runoob.com/cplusplus/cpp-tutorial.html