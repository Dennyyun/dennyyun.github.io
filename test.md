# 字符串与输入

## 转义字符

| 转义字符     | 描述       |
| :----------- | :--------- |
| \ (在行尾时) | 续航符     |
| \\           | 反斜杠符号 |
| \ '          | 单引号     |
| \ "          | 双引号     |
| \a           | 响铃       |
| \b           | 退格       |
| \000         | 空格       |
| \n           | 换行       |
| \v           | 纵向制表符 |
| \t           | 横向制表符 |
| \r           | 回车       |
| \f           | 换页       |



### 格式化字符串

`format`：格式如下

````py

print('今天是{}年{}月{}日'.format(2023,4,22))
````

效果如此：![](https://raw.githubusercontent.com/Denny2003/test-img/main/the1.png)

`f.formart`：格式如下

````py
year=2003
month=4
day=22
print(f'今天是{year}年{month}月{day}日')
````

效果如此：![](https://raw.githubusercontent.com/Denny2003/test-img/main/the1.png)



## 字符串输入

`input`：格式如下

````py
str=input('这是输入提示：')
str=int(input('这是输入提示：'))		#这是一个类型转换的例子，（转变为int类型）
````



### 字符串操作符

| 操作符 | 作用                                   |
| ------ | -------------------------------------- |
| +      | 连接两个字符串，返回连接结果           |
| *      | 重复一个字符串                         |
| in     | 判断字符串是否包含                     |
| not in | 判断字符串是否不包含                   |
| []     | 截取一个或一串字符串，这个操作叫做切片 |



### 字符串内建方法

| 方法名                            | 作用                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| count(sub[,start[,end]])          | 返回 sub 在字符串非重叠出现的次数，可选指定开始位置和结束位置 |
| find(sub[,start[,end]])           | 检查 sub 是否在字符串出现过，可选指定开始位置和结束位置      |
| isalpha()                         | 判断字符串是不是为空并且全是字母                             |
| isdigit()                         | 判断字符串是不是不为空并且全是数字                           |
| lstrip()                          | 截掉字符串左边的空格或指定字符                               |
| rstrip()                          | 截掉字符串右边的空格或指定字符                               |
| strip()                           | 同时截掉左右的空格或指定字符                                 |
| replace（old,new[,count]）        | 替换原字符中出现的 old 为 new，可指定最大替换次数            |
| index(sub[,start[,end]])          | 函数检测字符串中是否包含子字符串sub，可选指定开始位置和结束位置 |
| split（sep = None,maxsplit = -1） | 将字符串以sep字符为分隔符进行切片，如果sep未设置，则以maxsplit个空格为间隔 |
| upper()                           | 将字符串中的小写字母转为大写字母                             |
| lower()                           | 将字符串中的大写字母转为小写字母                             |
| len()                             | 获取字符串长度                                               |
| center(width[,fillchar])          | 原字符串居中，以fillchar（默认为空格）填充左右两边的字符串。 |
| startwith(sub[,start[end]])       | 判断字符串是否以sub 开始的字符串，可指定起止位置             |
| ：b、：o、：x                     | 分别为转为二进制、八进制、十六进制 输出                      |

# Tuple、List、Dict

## Tuple(元组)

> `Tuple`又叫元组，是一个线性结构，表达式如下

````py
tuple1=(1,2,3,4,5,6)
print(f'可以单独访问其中一个值：{tuple1[3]}')			#则这段代码会输出‘可以单独访问其中一个值：4’ 
````



### 切片

````py
#切片：头要尾不要
#格式如下
tuple1=(1,2,3,4,5,6)
print(tuple1[3])							#截取第四个元素，进行输出。
print(tuple1[0:3])						#截取连续的元素，输出：1~4。
print(tuple1[0:5:2])						#固定间隔截取元素，输出：（1、3、5）
````



### 修改   

> `Tuple`：的元素一旦指定就不可再修改，而可以通过创建一个新的`tuple`来实现修改
>
> 如以下例子：

````py
tuple1=(1,2,3,4,5,6)
tuple2=(7,8,9)
tuple3=tuple1+tuple2					#将tuple1与tuple2合并输出
print(tuple3)
tuple4=tuple1*2						    #将两个 tuple1 合并输出
print(tuple4)
````

> 效果如下：   ![](https://raw.githubusercontent.com/Denny2003/test-img/main/image-20230422232555761.png)



### 遍历

> 有两种一下方法

````py
#for循环遍历
for temp in tuple1:				 
    print(f'{temp}',end=' ')
    
#while循环遍历    
temp = 0
while temp < len(tuple1):
    print(f'{tuple1[temp]}',end=' ')
    temp += 1
````

> 效果如下：![](https://raw.githubusercontent.com/Denny2003/test-img/main/image-20230422232614767.png) 



### 查找

> 在`tupel`中查找元素可以用`in` 格式如下：

````py
if 2 in tuple1:
    print('We found 2!')
else:
    print('No 2!')
````



### 内置函数

````py
print(len(tuple1))			#求tuple的长度
print(max(tuple1))			#求tuple1中最大值
print(min(tuple1))			#求tuple1中最小值
````



## List（列表）

> List又叫列表，也是一个线性结构，表达式如下

````py
list1=[1,2,3,4,5,6]
````



### 添加

````py
list1.append(7)			#在list1 尾部添加一个元素，7
print(list1)

list2=[7,8,9,]
list1.extend(list2)			#将list2合并在list1后面输出
print(list1)
list1.insert(0,666)			#在头部添加添加 666
print(list1)
````

> 效果如下：![]()

### 删除



