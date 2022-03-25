# Python-Basic-Part1

<!--more-->
---
## 绪论
### Python的学习建议
- 多看多写，反复练习！

### Python的优点
* 代码行特别少，代码美观；
* 用的人多，找教程，找论坛非常方便，各种各样的包也丰富；
* 在提高工作效率的工具当中，它非常简单，容易上手；
---

## 安装与配置
**（以Windows10系统为例）**

**<font color="red">Step 1-Download: </font>** 前往[官方网站](https://www.python.org)，选中Python最新版本下载即可。

**<font color="red">Step 2-Installation: </font>** 双击运行名为“python-x.x.x-amd64.exe”的执行文件，全过程选择默认选项，可安装于C盘中，记得**勾选上“Install launcher for all users(recommended)”和“Add Python x.x to PATH”两个选项**。

**<font color="red">Step 3-Check: </font>** 按 Win + R 键调出运行，显示在左下角，输入`cmd`，在弹出的黑色输入框中输入`Python`，如果出现
```
Python 3.9.1 (tags/v3.9.1:1e5d33e, Dec  7 2020, 17:08:21) [MSC v.1927 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
恭喜，已成功安装Python。可尝试下述代码（这里`>>>`可理解为Word中的输入光标...`#`后为注释，说明之用）
```Python
>>>print("Hello World!")            # 输入这行，记得敲回车
Hello World!                        # 这都是显示的
>>>						            # 这都是显示的
```
{{< admonition note "为啥第一步都是Hello World呢？" false >}}
长期以来，编程界都认为刚接触一门新语言时，如果首先使用它来编写一个在屏幕上显示消息“Hello World！”的程序，将给你带来好运。
{{< /admonition >}}

---

## 编辑器的选择
编辑器有不少，如VS code，Geany，Atom，Sublime等。
{{< admonition note "编辑器是用来干啥的呢？" false >}}
写代码的。记事本也能写代码，也能写论文，但是我们还是会用Word写论文。同理，最好选一款编辑器来写代码！
{{< /admonition >}}

建议使用**Sublime**，[商业软件](https://www.sublimetext.com/)有钱的朋友可以支持一下，没钱的朋友[也不怕](https://pan.baidu.com/s/14ANQywO6orYuJL2-YKtNEA)，提取码2333。

大多数程序都可以直接从编辑器运行，但需要解决的问题比较复杂时，你编写的程序可能需要从终端运行。

---

## 基础小知识
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

6. 随着你编写的程序越来越长，有必要了解一些代码格式设置约定；

{{< admonition note "Python Enhancement Proposal, PEP" false>}}
PEP8是最古老的PEP之一，它向Python程序员提供了代码格式设置指南。PEP8的篇幅很长，但大都与复杂的编码结构相关。
1. 缩进；PEP8建议每级缩进都使用**四个空格**
2. 行长；很多Python程序员都建议每行**不超过80字符**；PEP8还建议注释的行长都不超过72字符
3. 空行；空行不会影响代码的运行，但会影响代码的可读性
{{< /admonition >}}

7. 避免犯小错误，例如不正确的缩进，冒号的遗漏等问题；

---

## 变量
**(Variable)**

### 变量是什么
举个简单的例子来理解变量
```Python
message = "Hello Python world!"
print(message)
```
运行结果和前面相同，这个`message`就是变量。其实，**变量**就是一个代号，一个名字，用来存储数据的。

### 变量怎么用
知道了什么是变量，下面介绍下如何正确使用变量：
1. 变量名只包含**字母**、**数字**和**下划线**。变量名可以字母或下划线打头，**但不可用数字打头**。例如：`message_1`是正确的，`1_message`是错误的；
2. 变量名**不可包含空格**，用下划线来分隔其中的单词。例如，`greeting_message`是正确的，`greeting message`是错误的；
3. **不要用Python关键字和函数名用作变量名**，例如：`print`就不能用于变量名；
4. 变量名应该简短且具有描述性；
5. 慎用小写字母l和大写字母O，因为可能被看错来。

{{< admonition note "用大写字母还是小写字母当变量名呢？" false >}}
就目前而言，应使用小写的Python变量名。在变量名中使用大写字母虽然不会导致错误，但避免使用大写字母是个不错的主意。PS，关键是小写大家看的懂，看着舒服，坦率地讲我看大写单词不舒服...
{{< /admonition >}}

### 变量有哪些

上面可以看到，`message`这个变量存了"balabalabala"一串乱七八糟的东西，这个东西称之为**字符串**(string format)。

#### 字符串
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

##### 字符串函数介绍
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

#### 数字
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
### 列表是什么
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
### 列表的操作
#### 列表的修改
列表的修改，例如
```Python
motorcycles = ['honda', 'yamaha', 'suzuki']    # ['honda', 'yamaha', 'suzuki']
motorcycles[0] = 'ducati'                      # ['ducati', 'yamaha', 'suzuki']
```
#### 元素的添加
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

#### 元素的删除
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
使用`remove()`删除元素时，也可以继续使用它的值。此外，`remove()`**只删除第一个指定的值**。

#### 组织列表
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

#### 遍历列表
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
#### 创建数值列表
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

#### 列表解析
**列表解析**将多行代码合并成一行，例如
```Python
squares = [value**2 for value in range(1,11)]  # [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

#### 切片
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

### 元组（特殊列表）
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
**对元组进行整体性的改动是合法的！**


---

## if语句
### if语句是什么
简单理解，就是判断对错~

示例
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
Python检查时，**<font color="red">区分大小写</font>**，`>>>'Audi' == 'audi'`为False。

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

### if语句
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
<font color="blue">**特别注意:**</font> 这个`else:`不写其实也行，但是建议还是写出来，因为有时候很有帮助~

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

### 测试多个条件
如下例所示，为测试多个条件
```Python
requested_toppings = ['mushrooms', 'extra cheese']

if 'mushrooms' in requested_toppings:
  print("Adding mushrooms.")
if 'pepperoni' in requested_toppings:
  print("Adding pepperoni.")
if 'extra cheese' in requested_toppings:
  print("Adding extra cheese.")

print("\nFinished making your pizza!")
```
得到结果
```code
Adding mushrooms.
Adding extra cheese.

Finished making your pizza!
```
将上述代码转变为if-elif-else结构，如下
```Python
requested_toppings = ['mushrooms', 'extra cheese']

if 'mushrooms' in requested_toppings:
  print("Adding mushrooms.")
elif 'pepperoni' in requested_toppings:
  print("Adding pepperoni.")
elif 'extra cheese' in requested_toppings:
  print("Adding extra cheese.")

print("\nFinished making your pizza!")
```
第一个测试检查时，就通过了，跳过了余下的部分，直至最后，显示如下
```code
Adding mushrooms.

Finished making your pizza!
```

### if语句处理列表
典型示例
```Python
available_toppings = ['mushrooms', 'olives', 'green peppers',
                      'pepperoni', 'pineapple', 'extra cheese']

requested_toppings = ['mushrooms', 'french fries', 'extra cheese']

for requested_topping in requested_toppings:
  if requested_topping in available_toppings:
    print("Adding " + requested_topping + ".")
  else:
    print("Sorry, we don't have " + requested_topping + ".")

print("\nFinished making your pizza!")
```
得到结果
```code
Adding mushrooms.
Sorry, we don't have french fries.
Adding extra cheese.

Finished making your pizza!
```
---

## 字典
### 字典是什么
来看一个游戏，其中包含一些外星人，这些外星人的颜色和点数各不相同。下面是一个简单的字典，存储了有关特定外星人的信息：
```Python
alien_0 = {'color': 'green', 'points': 5}

print(alien_0['color'])         #green
print(alien_0['points'])        #5
```
在Python中，**字典是一系列键-值对**。每个键都与一个值相关联，你可以使用键来访问与之相关联的值。与键相关联的值可以是数字、字符串、列表乃至字典。事实上，可将任何Python对象用作字典中的值。

### 字典怎么用
**创建一个空字典**
```Python
alien_0 = {}
```

**添加键-值对**
```Python
alien_0['x_position'] = 0
alien_0['y_position'] = 25
print(alien_0)                  #{'y_position': 25, 'x_position': 0}
```
**访问值**
```Python
print(alien_0['x_position'])    #0   ##访问值的方法
```

**修改字典中的值**
```Python
alien_0['x_position'] = 100
```

**删除键-值对**
```Python
del alien_0['x_position']       ##删除键
print(alien_0)                  #{'y_position': 25}
```
### 遍历字典
#### 遍历所有的键-值对

下面的字典存储一名用户的用户名、名和姓：
```Python
user_0 = {
    'username': 'efermi',
    'first': 'enrico',
    'last': 'fermi',
    }
```
可以使用一个for循环来遍历这个字典：
```Python
for key, value in user_0.items():
    print("\nKey: " + key)
    print("Value: " + value)
```
下面的代码使用了简单的变量名，这完全可行：
```Python
for k, v in user_0.items()
```
结果为
```Code
Key: last
Value: fermi

Key: first
Value: enrico

Key: username
Value: efermi
```
注意，即便遍历字典时，**键-值对的返回顺序也与存储顺序不同**。Python不关心键-值对的存储顺序，而只跟踪键和值之间的关联关系。

#### 遍历字典中的所有键

方法`keys()`很有用，下面来遍历字典`favorite_languages`，并将每个被调查者的名字都打印出来：
```Python
favorite_languages = {
  'jen': 'python',
  'sarah': 'c',
  'edward': 'ruby',
  'phil': 'python',
  }

for name in favorite_languages.keys():
  print(name.title())
```
遍历字典时，会默认遍历所有的键，因此，如果将上述代码中的`for name in favorite_languages.keys()`:替换为`for name in favorite_languages:`，输出将不变。

方法`keys()`并非只能用于遍历，实际上，**它返回一个列表**，其中包含字典中的所有键。

#### 按顺序遍历字典中的所有键

使用函数`sorted()`来获得按特定顺序排列的键列表的副本：
```Python
for name in sorted(favorite_languages.keys()):
  print(name.title() + ", thank you for taking the poll.")
```
这里类似于我先拿到键，然后进行排序。

#### 遍历字典中的所有值
使用方法`values()`，它返回一个值列表，而不包含任何键。

例如：`for language in favorite_languages.values():`

**为剔除重复项**，可使用集合`set`

例如：`for language in set(favorite_languages.values()):`

其实这里类似于重新生成了一个集合，或者列表，然后通过`for`进行遍历调用。

**随着你更深入地学习Python，经常会发现它内置的功能可帮助你以希望的方式处理数据。**

### 嵌套
有时候，需要将一系列字典存储在列表中，或将列表作为值存储在字典中，**这称为嵌套**。

#### 字典列表
下面的代码创建一个包含三个外 星人的列表：
```Python
alien_0 = {'color': 'green', 'points': 5}
alien_1 = {'color': 'yellow', 'points': 10}
alien_2 = {'color': 'red', 'points': 15}

aliens = [alien_0, alien_1, alien_2]

for alien in aliens:
  print(alien)

# Results
#{'color': 'green', 'points': 5}
#{'color': 'yellow', 'points': 10}
#{'color': 'red', 'points': 15}
```
在这个列表中，所有字典的结构都相同，因此你可以遍历这个列表，并以相同的方式处理其中的每个字典。

#### 在字典中存储列表
在本章前面有关喜欢的编程语言的示例中，如果将每个人的回答都存储在一个列表中，被调查者就可选择多种喜欢的语言。在这种情况下，当我们遍历字典时，与每个被调查者相关联的都是一个语言列表，而不是一种语言。
```Python
favorite_languages = {
  'jen': ['python', 'ruby'],
  'sarah': ['c'],
  'edward': ['ruby', 'go'],
  'phil': ['python', 'haskell'],
  }

for name, languages in favorite_languages.items():
  print("\n" + name.title() + "'s favorite languages are:")
  for language in languages:
    print("\t" + language.title())

#Jen's favorite languages are:
#   Python
#   Ruby

#Sarah's favorite languages are:
#   C

#Phil's favorite languages are:
#   Python
#   Haskell

#Edward's favorite languages are:
#   Ruby
#   Go
```

<font color="blue">**注意:**</font> 列表和字典的嵌套层级不应太多。如果嵌套层级比前面的示例多得多，很可能有更简单的解决问题的方案。

#### 在字典中存储字典
可在字典中嵌套字典，但这样做时，代码可能很快复杂起来。

```Python
users = {
  'aeinstein': {
      'first': 'albert',
      'last': 'einstein',
      'location': 'princeton',
      },

  'mcurie': {
      'first': 'marie',
      'last': 'curie',
      'location': 'paris',
      },

  }

for username, user_info in users.items():
  print("\nUsername: " + username)
  full_name = user_info['first'] + " " + user_info['last']
  location = user_info['location']

  print("\tFull name: " + full_name.title())
  print("\tLocation: " + location.title())
```
请注意，表示每位用户的字典的结构都相同，虽然Python并没有这样的要求，但这使得嵌套的字典处理起来更容易。倘若表示每位用户的字典都包含不同的键，for循环内部的代码将更复杂。

---

**（Part1部分到此结束）**

