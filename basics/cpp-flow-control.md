# 流程语句

# 1. 判断语句

## 1.1. if-else

格式

```c
if(boolean_expression)
{
   // 如果布尔表达式为真将执行的语句
}
else
{
   // 如果布尔表达式为假将执行的语句
}
```

示例

```c
// 检查布尔条件
if( a < 20 )
{
    // 如果条件为真，则输出下面的语句
    cout << "a 小于 20" << endl;
}
else
{
    // 如果条件为假，则输出下面的语句
    cout << "a 大于 20" << endl;
}
```

# 2. 循环语句

## 2.1. for

格式

```c
for ( init; condition; increment )
{
   statement(s);
}
```

示例

```c
// for 循环执行
for( int a = 10; a < 20; a = a + 1 )
{
    cout << "a 的值：" << a << endl;
}
```

## 2.2. while

格式

```c
while(condition)
{
   statement(s);
}
```

示例

```c
// while 循环执行
while( a < 20 )
{
    cout << "a 的值：" << a << endl;
    a++;
}
```

## 2.3. do...while

格式

```c
do
{
   statement(s);

}while( condition );
```

示例

```c
// do 循环执行
do
{
    cout << "a 的值：" << a << endl;
    a = a + 1;
}while( a < 20 );
```

## 2.4. break&continue

- break：跳出整个循环，执行循环后的语句。
- continue：跳出当前循环，执行下一个循环。

# 3. 选择语句

## 3.1. switch

格式

```c
switch(expression){
    case constant-expression  :
       statement(s);
       break; // 可选的
    case constant-expression  :
       statement(s);
       break; // 可选的
  
    // 您可以有任意数量的 case 语句
    default : // 可选的
       statement(s);
}
```

示例

```c
switch(grade)
{
case 'A' :
   cout << "很棒！" << endl; 
   break;
case 'B' :
case 'C' :
   cout << "做得好" << endl;
   break;
case 'D' :
   cout << "您通过了" << endl;
   break;
case 'F' :
   cout << "最好再试一下" << endl;
   break;
default :
   cout << "无效的成绩" << endl;
}
```



参考：

- https://www.tutorialspoint.com/cplusplus/index.htm
- https://www.runoob.com/cplusplus/cpp-tutorial.html