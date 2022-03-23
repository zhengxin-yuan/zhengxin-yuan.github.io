# Python-Basic

<!--more-->
{{< admonition note "学习建议" false>}}
多看多写，反复练习！
{{< /admonition>}}

## Python的优点
* 代码行特别少
* 用的人多，找教程，找论坛非常方便
* 提高工作效率的工具当中，它非常简单
---

## Python的安装与配置
**请于Windows10系统下进行**

**<font color="red">Step 01-Python的获取: </font>** 前往
[官网](https://www.python.org)进行下载。选中Downloads-当前Python的最新版本，下载即可。
过程简单无需附图。

**<font color="red">Step 02-Python的安装: </font>** 在上一步的最后，
你会获得一个名为“python-x.x.x-amd64.exe”的执行文件，在电脑中双击运行即可。
装的全过程选择默认选项即可，安装在C盘也是可以的。

**特别注意：** 一定要勾选上“Install launcher for all users(recommended)”和
“Add Python x.x to PATH”两个选项哦，避免不必要的麻烦。

**<font color="red">Step 03-检查是否成功: </font>** 按 Win + R 键调出运行，
显示在左下角，输入`cmd`，在弹出的黑色输入框中输入`Python`，如果出现
```Python
Python 3.9.1 (tags/v3.9.1:1e5d33e, Dec  7 2020, 17:08:21) [MSC v.1927 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
那么恭喜你，你已成功安装上了Python。你可以尝试敲入下述代码（这里的`>>>`可以理解为输入光标...`#`后的内容是注释，给你看的，别敲进去了...）
```Python
>>>print("Hello World!")            # 输入这行，记得敲回车
Hello World!                        # 这都是显示的
>>>						            # 这都是显示的
```
{{< admonition note "为啥第一步都是Hello World呢？" false >}}
长期以来，编程界都认为刚接触一门新语言时，如果首先使用它来编写一个在屏幕上显示消息“Hello World！”的程序，将给你带来好运。
{{< /admonition >}}

---

## Python的编辑器
各种各样的编辑器有很多，例如VS code，Geany，Atom，Sublime等等。当然，大佬可以选择用记事本来写代码。
{{< admonition note "编辑器是用来干啥的呢？" false >}}
写字的，写代码的。记事本也能写代码，也能写论文，但是我们还是会用Word写论文，嘻嘻嘻！
{{< /admonition >}}

作者建议使用Sublime，这里只提供[官网链接](https://www.sublimetext.com/)，是个商业软件，不购买就给你弹广告，有钱的朋友可以支持一下，没钱的朋友麻烦百度一下。**下面就假设你自己弄好了。**

大多数程序都可以直接从编辑器运行，但需要解决的问题比较复杂时，你编写的程序可能需要从终端运行。

---

## 不可不知的小知识
1. Python文件的后缀为`.py`，类似于Word的文件后缀为`.docx`或`.doc`，PPT的文件后缀为`.pptx`或`.ppt`，Matlab的文件后缀为`.m`，游戏的快捷方式后缀为`.exe`；
2. 编辑器会以各种方式突出代码的不同部分。例如`print`是一个函数的名称，其颜色会与其他代码不同；
3. 代码中的一些小的错误可以通过traceback进行修改；

{{< admonition note "啥是traceback呢？" false>}}
traceback是一条记录，指出了解释器尝试运行代码时，在什么地方陷入了困境。
```
Traceback (most recent call last):
  File "hello_world.py", line 2, in <module>
    print(mesage)							   // 说明你这变量没定义，如果你觉得自己定义了，
NameError: name 'mesage' is not defined        // 说明这个地方单词写错了，也就是变量名错了
```
上述例子意味着两种情况：要么是使用变量前忘记了给它赋值，要么是输入变量名时拼写不正确。
{{< /admonition >}}

4. 一个好的编辑器非常重要；

{{< admonition note "编辑器有啥用呢？" false>}}
编写程序时，编辑器的语法突出功能可帮助你快速找出某些语法错误。发现不匹配的情况。
{{< /admonition >}}

5. Python顺序索引是从0开始的，俗话说的好，Python从零开始上天梯~

6. 随着你编写的程序越来越长，有必要了解一些代码格式设置约定。

{{< admonition note "Python Enhancement Proposal, PEP" false>}}
PEP8是最古老的PEP之一，它向Python程序员提供了代码格式设置指南。PEP8的篇幅很长，但大都与复杂的编码结构相关。
1. 缩进；PEP8建议每级缩进都使用**四个空格**
2. 行长；很多Python程序员都建议每行**不超过80字符**；PEP8还建议注释的行长都不超过72字符
3. 空行；空行不会影响代码的运行，但会影响代码的可读性
{{< /admonition >}}

---

## 变量
**(Variable)**

举个简单的例子来理解变量
```Python
message = "Hello Python world!"
print(message)
```
运行结果和前面相同，这个`message`就是变量。其实，**变量**就是一个代号，一个名字，用来存储数据的。

知道了什么是变量，下面介绍下如何以正确的姿势来使用变量：
1. 变量名只包含**字母**、**数字**和**下划线**。变量名可以字母或下划线打头，但不可用数字打头。例如：`message_1`是正确的，`1_message`是错误的；
2. 变量名不可包含空格，用下划线来分隔其中的单词。例如，`greeting_message`是正确的，`greeting message`是错误的；
3. 不要用Python关键字和函数名用作变量名，例如：`print`就不能用于变量名；
4. 变量名应该简短且具有描述性；
5. 慎用小写字母l和大写字母O，因为可能被看错来。

{{< admonition note "用大写字母还是小写字母当变量名呢？" false >}}
就目前而言，应使用小写的Python变量名。在变量名中使用大写字母虽然不会导致错误，但避免使用大写字母是个不错的主意。PS，关键是小写大家看的懂，看着舒服，坦率地讲我看大写单词不舒服...
{{< /admonition >}}

上面可以看到，`message`这个变量存了"balabalabala"一串乱七八糟的东西，这个东西程序员称之为**字符串**(string format)

### 字符串
**(String Format)**

单双引号都可以引入字符串，例如
```Python
"Hello Python world!"
'Hello Python world!'
```
这样做是为了句子中带引号，例如
```Python
'I told my friend, "Python is my favorite language!"'
```

### 字符串函数介绍
`.title()`、`.upper()`、`.lower()`函数，举例说明
```Python
>>>name = "aDa lovElAce nicE"
>>>print(name.title())
>>>print(name.upper())
>>>print(name.lower())

Ada Lovelace Nice                     # 输出结果
ADA LOVELACE NICE                     # 输出结果
ada lovelace nice                     # 输出结果
```
`+`命令，合并字符串，举例说明
```Python
>>>first_name = "zhEngxin"
>>>last_name = "YUAn"
>>>full_name = first_name.title() + " " + last_name.upper()
>>>print(full_name)

Zhengxin YUAN                         # 输出结果
```
`\t`和`\n`命令，举例说明
```Python
>>>print("\tPython")
>>>print("\nC\nC++\nJava")

	Python                            # 输出结果

C                                     # 输出结果
C++                                   # 输出结果
Java                                  # 输出结果
```
`.rstrip()`、`.lstrip()`、`.strip()`用于删除空白，举例说明
```Python
>>>language = ' python '
>>>language.rstrip()
' python'
>>>language.lstrip()
'python '
>>>language.strip()
'python'
```

### 数字
上述例子中，我们不断地输入各种句子或单词，那我们可以把Python当作计算器么？毫无疑问，**是可以的**。

整数计算，加减乘除，举例说明
```Python
>>> 2 + 3
5
>>> 3 - 2
1
>>> 2 * 3
6
>>> 3 / 2
1.5
```
乘方与运算顺序，举例说明
```Python
>>> 3 ** 3
27
>>> 10 ** 6
1000000
>>> 2 + 3 * 4
14
>>> (2 + 3) * 4
20
```

浮点数计算，加减乘除，举例说明
```Python
>>> 0.1 + 0.1
0.2
>>> 0.2 - 0.2
0.4
>>> 2 * 0.1
0.2
>>> 2 * 0.2
0.4
```

`str()`转型，举例说明
```Python
age = 23
message = "Happy " + str(age) + "rd Birthday!"
print(message)

Happy 23rd Birthday!          #输出结果
```

{{< admonition note "注释有啥用呢？" false >}}
注释用井号`#`标识。编写注释的主要目的是阐述代码要做什么，以及是如何做的。
{{< /admonition >}}

---
## 列表
### 列表的生成与访问
列表是由一系列按特定顺序排列的元素组成。综合例子
```Python
bicycles = ["trek",'cannondale','redline','specialized']     #单双引号均可，混用也可
print(bicycles)
print(bicycles[0])                                           #索引从0开始
print(bicycles[1])
print(bicycles[3].title())
print(bicycles[-1])                                          #倒序索引
```
输出结果
```Python
['trek', 'cannondale', 'redline', 'specialized']
trek
cannondale
Specialized
specialized
```

### 列表的修改
列表的修改，例如
```Python
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
motorcycles[0] = 'ducati'                      # ['ducati', 'yamaha', 'suzuki']
```
### 元素的添加
元素的添加，例如
```Python
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
motorcycles.append('ducati')                   # ['honda', 'yamaha', 'suzuki', 'ducati']
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
motorcycles.insert(0, 'ducati')                # ['ducati', 'honda', 'yamaha', 'suzuki']
```

{{< admonition note "append()的好处" false >}}
这种创建列表的方式极其常见，因为经常要等程序运行后，你才知道用户要在程序中存储哪些数据。
{{< /admonition >}}

### 元素的删除
`del`删除列表中的元素，例如
```Python
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
del motorcycles[0]                             # ['yamaha', 'suzuki']
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
del motorcycles[1]                             # ['honda', 'suzuki']
# 在这两个示例中，使用del语句将值从列表中删除后，就无法再访问它了
```
`pop()`删除元素，例如
```Python
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
popped_motorcycle = motorcycles.pop()          # ['honda', 'yamaha']
print(popped_motorcycle)                       # suzuki
```
此为弹出最后一个数据。如果想弹出任意位置，在括号内添加索引即可。例如
```Python
popped_motorcycle = motorcycles.pop(0)         # ['yamaha', 'suzuki']
```
`remove()`根据值删除元素，例如
```Python
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
motorcycles.remove('suzuki')                   # ['honda', 'yamaha']
```
使用`remove()`删除元素时，也可以继续使用它的值。此外，`remove()`只删除第一个指定的值。

### 组织列表
`sort()`对列表永久性排序，例如
```Python
cars = ['bmw', 'audi', 'toyota', 'subaru']     # ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()                                    # ['audi', 'bmw', 'subaru', 'toyota']
cars.sort(reverse=True)                        # ['toyota', 'subaru', 'bmw', 'audi']
```
`sorted()`对列表临时性排序，例如
```Python
print(sorted(cars))                            # ['audi', 'bmw', 'subaru', 'toyota']
print(sorted(cars), reverse=True)              # ['toyota', 'subaru', 'bmw', 'audi']
```
`reverse()`反转列表元素，例如
```Python
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
motorcycles.reverse()                          # ['suzuki', 'yamaha', 'honda']
```
注意，这里时**反转列表**不是排序列表！

`len()`确定列表的长度，例如
```Python
len(motorcycles)                               # 3
```

### 遍历列表
`for`循环，可遍历列表，例如
```Python
magicians = ['alice', 'daivd', 'carolina']
for magician in magicians:                     # 这个magician可以换成别的xx都行
	print(magician)                            # 这里magician需要配套进行变化
# alice                                        # 当然有意义的名称帮助大些
# daivd
# carolina
```
循环中的更多操作，例如
```Python
magicians = ['alice', 'daivd', 'carolina']
for magician in magicians:                     # 注意冒号问题！
print(magician)                                # 忘记缩进 错误！！！
	print(magician)                            # 正确
	print(magician.title() + " is great!")     # 循环中的其他操作
```

---
## 数值列表
`range()`可打印一系列的数字，例如
```Python
for value in range(1,3):
	print(value)
# 1
# 2                                            # 实际上不会打印数字3
```

`list()`可形成数字列表，例如
```Python
numbers = list(range(1,6))                     # [1, 2, 3, 4, 5]
even_number = list(range(2,11,2))              # [2, 4, 6, 8, 10]
```
简单例子
```Python
squares = []
for value in range(1,11):
	squares.append(value**2)
print(squares)                                 # [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
`min`、`max`、`sum`简单统计
```Python
min(squares)                                   # 1
max(squares)                                   # 100
sum(squares)                                   # 385
```

### 列表解析
**列表解析**将多行代码合并成一行，例如
```Python
squares = [value**2 for value in range(1,11)]  # [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

### 切片
**切片**是提取列表的部分元素，例如
```Python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[0:3])            # ['charles', 'martina', 'michael']
print(players[1:4])            # ['martina', 'michael', 'florence']
print(players[:4])             # ['charles', 'martina', 'michael', 'florence']
print(players[2:])             # ['michael', 'florence', 'eli']
print(players[-3:])            # ['michael', 'florence', 'eli']
```
遍历切片，例如
```Python
for player in players[:3]:
	print(player.title())
```
复制列表，例如
```Python
my_players = players[:]
my_players = players           # 这个行不通，只是取别名
```

---
## 元组
不可变的列表被称为**元组**。
```Python
dimensions = (200, 50)         # 元组定义
print(dimensions[0])           # 索引 200
print(dimensions[1])           # 索引 50
dimensions[0] = 250            # 报错！ 无法修改
dimensions = (250, 100)        # 可整体修改
for dimension in dimensions:
	print(dimension)           # 遍历元组中的所有值
```

---

## if语句
简单理解，就是判断对错~

简单示例
```Python
cars = ['audi', 'bmw', 'subaru', 'toyota']
for car in cars:
	if car == 'bmw':           # 只有宝马大写！
		print(car.upper())
	else:
		print(car.title())
# Audi
# BMW
# Subaru
# Toyota
```
Python检查相等时**区分大小写**，`>>>'Audi' == 'audi'`为False。

`!=`用于检查不相等。`<`为小于，`<=`为小于等于，`>`为大于，`>=`为大于等于。

`and`与`or`检查多个条件`age_0 >= 21 and age_1 >= 21`或`age_0 >= 21 or age_1 >= 21`基本理解

`(age_0 >= 21) and (age_1 >= 21)`加个括号提高可读性!

`in`的使用，`1 in list(range(1,10))`结果为`True`

`not in`的使用同理，`1 not in list(range(1,10))`结果为`False`

<br>

**布尔表达式**，给变量赋值`True`or`False`，例如
```Python
game_active = True
can_edit = False
```

### 简单的if语句
```Python
if conditional_test:           # 一定记得写冒号哦！
	do something               # 记得缩进！
```

### if-else语句
```Python
if conditional_test:           # 一定记得写冒号哦！
	do something               # 记得缩进！
else:
	do something               # 也记得加冒号！
```

### if-elif-else结构
```Python
if conditional_test1:          # 一定记得写冒号哦！
	do something               # 记得缩进！
elif conditional_test2:
	do something               # 也记得加冒号！
elif conditional_test3:
	do something
# 更多
else:
	do something               # 自己根据需要精简代码哦~
```
<font color="blue">**特别注意:**</font> 这个`else:`不写其实也行，但是建议还是写出来，
因为有时候很有帮助~

特殊例子
```Python
name_cars = []

if name_cars:                  # 只要列表不为空，这个地方就是True
	do something
else:
	do something
```

{{< admonition note "如何使Python代码好看？" false>}}
在诸如`==`、`>=`和`<=`等比较运算符两边各添加一个空格，例如，`if age < 4:`要比`if age<4:`好！
这样的空格不会影响Python对代码的解读，而只是让代码阅读起来更容易。
{{< /admonition >}}

