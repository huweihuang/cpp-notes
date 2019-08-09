# 数据类型

# 1. 变量

## 1.1. 变量定义

### 1.1.1. 变量声明

```c++
<type> <variable_list>;
```

- type：表示声明变量的数据类型。
- variable_list：表示变量的名字，可以多个。

例如：

```c++
int    i, j, k;
char   c, ch;
float  f, salary;
double d;
```

### 1.1.2. 声明并初始化

```c++
<type> <variable_name> = <value>;
```

例如：

```c++
extern int d = 3, f = 5;    // d 和 f 的声明 
int d = 3, f = 5;           // 定义并初始化 d 和 f
byte z = 22;                // 定义并初始化 z
char x = 'x';               // 变量 x 的值为 'x'
```

## 1.2. 变量类型

| 类型     | 关键字  |
| :------- | :------ |
| 布尔型   | bool    |
| 字符型   | char    |
| 整型     | int     |
| 浮点型   | float   |
| 双浮点型 | double  |
| 无类型   | void    |
| 宽字符型 | wchar_t |

### 1.2.1. 整型

### 1.2.2. 浮点型

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

```c++
// define格式
#define identifier value

// 例如
#define LENGTH 10   
#define WIDTH  5
#define NEWLINE '\n'
```

- 使用 **const** 关键字。

```c++
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

## 数组



## 字符串



## 指针



## 引用



## 结构体(struct)



# 4. 特殊类型





参考：

- https://www.tutorialspoint.com/cplusplus/index.htm
- https://www.runoob.com/cplusplus/cpp-tutorial.html