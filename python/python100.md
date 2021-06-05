私有属性：__ （两个下划线） 外部不能访问



受保护属性：_（一个下划线）可以访问修改



- `chr()`：将整数转换成该编码对应的字符串（一个字符）。

- `ord()`：将字符串（一个字符）转换成对应的编码（整数）。

  

| 运算符                                          | 描述                           |
| ----------------------------------------------- | ------------------------------ |
| `[]` `[:]`                                      | 下标，切片                     |
| `**`                                            | 指数                           |
| `~` `+` `-`                                     | 按位取反, 正负号               |
| `*` `/` `%` `//`                                | 乘，除，模，整除               |
| `+` `-`                                         | 加，减                         |
| `>>` `<<`                                       | 右移，左移                     |
| `&`                                             | 按位与                         |
| `^` `|`                                         | 按位异或，按位或               |
| `<=` `<` `>` `>=`                               | 小于等于，小于，大于，大于等于 |
| `==` `!=`                                       | 等于，不等于                   |
| `is` `is not`                                   | 身份运算符                     |
| `in` `not in`                                   | 成员运算符                     |
| `not` `or` `and`                                | 逻辑运算符                     |
| `=` `+=` `-=` `*=` `/=` `%=` `//=` `**=` `&=` ` | =` `^=` `>>=` `<<=`            |



**python中字符串的格式化分为两种：%和format**  



**函数：**在调用函数的时候如果没有传入对应参数的值时将使用该参数的默认值

在不确定参数个数的时候，我们可以使用可变参数：

```python
# 在参数名前面的*表示args是一个可变参数
def add(*args):
    total = 0
    for val in args:
        total += val
    return total


# 在调用add函数时可以传入0个或多个参数
print(add())
print(add(1))
print(add(1, 2))
print(add(1, 2, 3))
print(add(1, 3, 5, 7, 9))
```



**用模块管理函数**

Python中每个文件就代表了一个模块

如果我们导入的模块除了定义函数之外还有可以执行代码，那么Python解释器在导入这个模块时就会执行这些代码，事实上我们可能并不希望如此，因此如果我们在模块中编写了执行代码，最好是将这些执行代码放入如下所示的条件中，这样的话除非直接运行该模块，if条件下的这些代码是不会执行的，因为只有直接执行的模块的名字才是"__main__"。



python有一个内置属性，一个模块在上下文中的名字：**__\*name\*__**

1° 当文件被执行时，__*name_*_*='__main*__'；

2° 当文件被调用时，__*name*__*='模块名'。*

```python
'''这是一个模块'''
def main():
    # code...
if  __name__='__main__':
    main( )
```

调试代码的时候，在”if __name__ == ‘__main__’“中加入一些我们的调试代码，我们可以让外部模块调用的时候不执行我们的调试代码，但是如果我们想排查问题的时候，直接执行该模块文件，调试代码能够正常运行



YIELD:https://blog.csdn.net/mieleizhi0522/article/details/82142856/



面向对象：封装，继承，多态