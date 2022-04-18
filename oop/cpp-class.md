# 1. 函数

## 1.1. 定义

```c
return_type function_name( parameter list )
{
   body of the function
}
```

示例

```c
// 函数返回两个数中较大的那个数
int max(int num1, int num2) 
{
   // 局部变量声明
   int result;

   if (num1 > num2)
      result = num1;
   else
      result = num2;

   return result; 
}
```

# 2. 类

## 2.1. 属性

```c
class Box
{
   // 公有的属性，类外部可以通过`.`的符号来访问 
   public:
      double length;
      void setWidth( double wid );
      double getWidth( void );
   // 私有属性，类外部不能访问，也不能被派生类访问，可以通过类的get方法访问
   private:
      double width;
   // 保护属性，保护属性可以被本类和派生的子类访问
   protected:
      double height;
};
```

## 2.2. 方法

**内联的方式，定义在类的内部。**

```c
class Box
{
   public:
      double length;      // 长度
      double breadth;     // 宽度
      double height;      // 高度

      double getVolume(void)   // 公有的方法
      {
         return length * breadth * height;
      }
};
```

**通过范围解析符 :: 来定义**

```c
double Box::getVolume(void)
{
    return length * breadth * height;
}
```

**调用方法**

```c
// 创建一个对象
Box myBox;          
// 调用该对象的成员函数
myBox.getVolume();  
```

### `::`和`->`的使用

c++中如果定义的类对象是指针对象的时候，用`->`来指向类中的成员；如果类对象是一般对象则用`.`来指向类中的成员。

```cpp
class A
{　　
    public play();
}


A *p则使用：p->play(); // 左边是结构指针。
A p 则使用：p.paly(); // 左边是结构变量。
```

`::`域操作符的用法

- 在类外部声明成员函数。void A::Print(){};

## 2.3. 构造函数

类的**构造函数**是类的一种特殊的成员函数，它会在每次创建类的新对象时执行。

构造函数的名称与类的名称是完全相同的，并且不会返回任何类型，也不会返回 void。构造函数可用于为某些成员变量设置初始值。

```c
#include <iostream>

using namespace std;

class Line
{
   public:
      void setLength( double len );
      double getLength( void );
      Line(double len);  // 这是构造函数

   private:
      double length;
};

// 成员函数定义，包括构造函数
Line::Line( double len)
{
    cout << "Object is being created, length = " << len << endl;
    length = len;
}

void Line::setLength( double len )
{
    length = len;
}

double Line::getLength( void )
{
    return length;
}
// 程序的主函数
int main( )
{
   Line line(10.0);

   // 获取默认设置的长度
   cout << "Length of line : " << line.getLength() <<endl;
   // 再次设置长度
   line.setLength(6.0); 
   cout << "Length of line : " << line.getLength() <<endl;

   return 0;
}
```

## 2.4. 析构函数

类的**析构函数**是类的一种特殊的成员函数，它会在每次删除所创建的对象时执行。

析构函数的名称与类的名称是完全相同的，只是在前面加了个波浪号（~）作为前缀，它不会返回任何值，也不能带有任何参数。析构函数有助于在跳出程序（比如关闭文件、释放内存等）前释放资源。

```c
#include <iostream>

using namespace std;

class Line
{
   public:
      void setLength( double len );
      double getLength( void );
      Line();   // 这是构造函数声明
      ~Line();  // 这是析构函数声明

   private:
      double length;
};

// 成员函数定义，包括构造函数
Line::Line(void)
{
    cout << "Object is being created" << endl;
}
Line::~Line(void)
{
    cout << "Object is being deleted" << endl;
}

void Line::setLength( double len )
{
    length = len;
}

double Line::getLength( void )
{
    return length;
}
// 程序的主函数
int main( )
{
   Line line;

   // 设置长度
   line.setLength(6.0); 
   cout << "Length of line : " << line.getLength() <<endl;

   return 0;
}
```

参考：

- https://www.tutorialspoint.com/cplusplus/index.htm
- https://www.runoob.com/cplusplus/cpp-tutorial.html