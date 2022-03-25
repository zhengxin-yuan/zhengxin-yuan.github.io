# Python-Basic-Part2

<!--more-->
---
## 用户输入
### 用户输入是什么
函数`input()`让程序暂停运行，等待用户输入一些文本。获取用户输入后，Python将其存储在一个变量中，以方便你使用。
```Python
message = input("Tell me something, and I will repeat it back to you: ")
print(message)  
```
得到
```Code
Tell me something, and I will repeat it back to you: Hello everyone!
Hello everyone!
```
<font color="blue">**注意:**</font> Sublime Text**不能运行提示用户输入的程序**。你可以使用Sublime Text来编写提示用户输入的程序，但必须从终端运行它们。

可将提示存储在一个变量中，再将该变量传递给函数`input()`。

```Python
prompt = "If you tell us who you are, we can personalize the messages you see."
prompt += "\nWhat is your first name? "

name = input(prompt)
print("\nHello, " + name + "!")
```

### 获取数值输入
使用函数`int()`实现
```Python
height = input("How tall are you, in inches? ")
height = int(height)

if height >= 36:
    print("\nYou're tall enough to ride!")
else:
    print("\nYou'll be able to ride when you're a little older.")
```

### 求模运算符
处理数值信息时，求模运算符（`%`）是一个很有用的工具，它将两个数相除并返回余数：
```Python
>>> 4 % 3
1
>>> 5 % 3
2
>>> 6 % 3
0
>>> 7 % 3
1
```

---

## while 循环
### while 循环是什么
for循环用于针对集合中的每个元素都一个代码块，而while循环不断地运行，直到指定的条件不满足为止。

### while 循环怎么用
你可以使用while循环来数数，例如，下面的while循环从1数到5：
```Python
current_number = 1
while current_number <= 5:
    print(current_number)
    current_number += 1

#1
#2
#3
#4
#5
```

### 让用户选择何时退出
可使用while循环让程序在用户愿意时不断地运行，如下面的程序
```Python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "

message = ""
while message != 'quit':
    message = input(prompt)

    if message != 'quit':
        print(message)

#Tell me something, and I will repeat it back to you:
#Enter 'quit' to end the program. Hello everyone!
#Hello everyone!

#Tell me something, and I will repeat it back to you:
#Enter 'quit' to end the program. Hello again.
#Hello again.

#Tell me something, and I will repeat it back to you:
#Enter 'quit' to end the program. quit
```

#### 使用标志
可定义一个变量，用于判断整个程序是否处于活动状态，这个变量被称为**标志**。
```Python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "

active = True
while active:
    message = input(prompt)

    if message == 'quit':
        active = False
    else:
        print(message)
```

#### 使用 break 退出循环
要立即退出while循环，不再运行循环中余下的代码，也不管条件测试的结果如何，可使用break语句。
```Python
prompt = "\nPlease enter the name of a city you have visited:"
prompt += "\n(Enter 'quit' when you are finished.) "

while True:
    city = input(prompt)

    if city == 'quit':
        break
    else:
        print("I'd love to go to " + city.title() + "!")

#Please enter the name of a city you have visited:
#(Enter 'quit' when you are finished.) New York
#I'd love to go to New York!

#Please enter the name of a city you have visited:
#(Enter 'quit' when you are finished.) San Francisco
#I'd love to go to San Francisco!

#Please enter the name of a city you have visited:
#(Enter 'quit' when you are finished.) quit
```

<font color="blue">**注意:**</font> 在任何Python循环中都可使用`break`语句。例如，可使用break语句来退出遍历列表或字典的for循环。

### 在循环中使用 continue
要返回到循环开头，并根据条件测试结果决定是否继续执行循环，可使用`continue`语句，它不像`break`语句那样不再执行余下的代码并退出整个循环。
```Python
current_number = 0
while current_number < 10:
    current_number += 1
    if current_number % 2 == 0:
        continue

    print(current_number)

#1
#3
#5
#7
#9
```
如果结果为0（意味着`current_number`可被2整除），就执行`continue`语句， 让Python忽略余下的代码，并返回到循环的开头。

### 避免无限循环
每个`while`循环都必须有停止运行的途径，这样才不会没完没了地执行下去。

**如果程序陷入无限循环，可按Ctrl + C，也可关闭显示程序输出的终端窗口。**

<font color="blue">**注意:**</font> 有些编辑器（如Sublime Text）内嵌了输出窗口，这可能导致难以结束无限循环，因此不 得不关闭编辑器来结束无限循环。

### 使用 while 循环来处理列表和字典
到目前为止，我们每次都只处理了一项用户信息：获取用户的输入，再将输入打印出来或作出应答；循环再次运行时，我们获悉另一个输入值并作出响应。然而，要记录大量的用户和信息，需要在while循环中使用列表和字典。

#### 在列表之间移动元素
使用一个`while`循环，在验证用户的同时将其从未验证用户列表中提取出来，再将其加入到另一个已验证用户列表中。代码可能类似于下面这样：
```Python
unconfirmed_users = ['alice', 'brian', 'candace']
confirmed_users = []

while unconfirmed_users:
    current_user = unconfirmed_users.pop()

    print("Verifying user: " + current_user.title())
    confirmed_users.append(current_user)

print("\nThe following users have been confirmed:")
for confirmed_user in confirmed_users:
    print(confirmed_user.title())

#Verifying user: Candace
#Verifying user: Brian
#Verifying user: Alice

#The following users have been confirmed:
#Candace
#Brian
#Alice
```

#### 删除包含特定值的所有列表元素
假设你有一个宠物列表，其中包含多个值为'cat'的元素。要删除所有这些元素，可不断运行一个`while`循环，直到列表中不再包含值'cat'，如下所示：
```Python
pets = ['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
print(pets)

while 'cat' in pets:
    pets.remove('cat')

print(pets)

#['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
#['dog', 'dog', 'goldfish', 'rabbit']
```

#### 使用用户输入来填充字典
可使用`while`循环提示用户输入任意数量的信息。
```Python
responses = {}

polling_active = True

while polling_active:
    name = input("\nWhat is your name? ")
    response = input("Which mountain would you like to climb someday? ")

    responses[name] = response

    repeat = input("Would you like to let another person respond? (yes/ no) ")
    if repeat == 'no':
        polling_active = False

print("\n--- Poll Results ---")
for name, response in responses.items():
    print(name + " would like to climb " + response + ".")


# What is your name? Eric
# Which mountain would you like to climb someday? Denali
# Would you like to let another person respond? (yes/ no) yes

# What is your name? Lynn
# Which mountain would you like to climb someday? Devil's Thumb
# Would you like to let another person respond? (yes/ no) no

# --- Poll Results ---
# Lynn would like to climb Devil's Thumb.
# Eric would like to climb Denali.
```

---

## 函数
### 函数是什么
函数是带名字的代码块，用于完 成具体的工作。

### 函数怎么用
下面是一个打印问候语的简单函数，名为greet_user()：
```Python
def greet_user():
    print("Hello!")

greet_user()

# Hello!
```
这个示例演示了最简单的函数结构。在这里，函数名为`greet_user()`，它不需要任何信息就能完成其工作，因此括号是空的（即便如此，括号也必不可少）。最后，定义以冒号结尾。

紧跟在`def greet_user():`后面的所有缩进行构成了**函数体**，描述了函数是做什么的。

#### 向函数传递信息
通过在这里添加username，就可让函数接受你给username指定的任何值。
```Python
def greet_user(username):
    print("Hello, " + username.title() + "!")

greet_user('jesse')

# Hello, Jesse!
```

#### 实参和形参
在函数`greet_user()`的定义中，变量`username`是一个**形参**，函数完成其工作所需的一项信息。在代码`greet_user('jesse')`中，值`'jesse'`是一个**实参**。**实参**是调用函数时传递给函数的信息。我们调用函数时，将要让函数使用的信息放在括号内。在`greet_user('jesse')`中，将实参`'jesse'`传递给了函数`greet_user()`，这个值被存储在形参`username`中。

<font color="blue">**注意:**</font> 大家有时候会形参、实参不分，因此如果你看到有人将函数定义中的变量称为实参或将函数调用中的变量称为形参，不要大惊小怪。

### 传递实参
#### 位置实参
你调用函数时，Python必须将函数调用中的每个实参都关联到函数定义中的一个形参。为此，最简单的关联方式是基于实参的顺序。这种关联方式被称为**位置实参**。
```Python
def describe_pet(animal_type, pet_name):
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet('hamster', 'harry')
describe_pet('dog', 'willie')

# I have a hamster.
# My hamster's name is Harry.

# I have a dog.
# My dog's name is Willie.
```
**位置实参的顺序很重要!**

#### 关键字实参
**关键字实参**是传递给函数的名称-值对，你直接在实参中将名称和值关联起来。
```Python
def describe_pet(animal_type, pet_name):
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet(animal_type='hamster', pet_name='harry')
describe_pet(pet_name='harry', animal_type='hamster')
```
<font color="blue">**注意:**</font> 使用关键字实参时，务必准确地指定函数定义中的形参名。

#### 默认值
例如，如果你发现调用`describe_pet()`时，描述的大都是小狗，就可将形参`animal_type`的默认值设置为`'dog'`。这样，调用`describe_pet()`来描述小狗时，就可不提供这种信息：
```Python
def describe_pet(pet_name, animal_type='dog'):
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet(pet_name='willie')

# I have a dog.
# My dog's name is Willie.
```
<font color="blue">**注意:**</font> 使用默认值时，在形参列表中**必须先列出没有默认值的形参**，再列出有默认值的实参。这让Python依然能够正确地解读位置实参。

#### 等效的函数调用
鉴于可混合使用位置实参、关键字实参和默认值，通常有多种等效的函数调用方式。
```Python
describe_pet('willie')
describe_pet(pet_name='willie')

describe_pet('harry', 'hamster')
describe_pet(pet_name='harry', animal_type='hamster')
describe_pet(animal_type='hamster', pet_name='harry')
```
这些函数调用的输出与前面的示例相同。

<font color="blue">**注意:**</font> 使用哪种调用方式无关紧要，只要函数调用能生成你希望的输出就行。使用对你来说最容易理解的调用方式即可。

#### 避免实参错误
```Python
def describe_pet(animal_type, pet_name):
    print("\nI have a " + animal_type + ".")
    print("My " + animal_type + "'s name is " + pet_name.title() + ".")

describe_pet()
```
Python发现该函数调用缺少必要的信息，而traceback指出了这一点：
```Code
Traceback (most recent call last):
  File "pets.py", line 6, in <module>
    describe_pet()
TypeError: describe_pet() missing 2 required positional arguments: 'animal_
type' and 'pet_name'
```

### 返回值
函数并非总是直接显示输出，相反，它可以处理一些数据，并返回一个或一组值。
#### 返回简单值
下面来看一个函数，它接受名和姓并返回整洁的姓名：
```Python
def get_formatted_name(first_name, last_name):
    full_name = first_name + ' ' + last_name
    return full_name.title()

musician = get_formatted_name('jimi', 'hendrix')
print(musician)

# Jimi Hendrix
```

#### 让实参变成可选的
让中间名变成可选的，可给实参`middle_name`指定一个默认值，空字符串。
```Python
def get_formatted_name(first_name, last_name, middle_name=''):
    if middle_name:
        full_name = first_name + ' ' + middle_name + ' ' + last_name
    else:
      full_name = first_name + ' ' + last_name
    return full_name.title()

musician = get_formatted_name('jimi', 'hendrix')
print(musician)

musician = get_formatted_name('john', 'hooker', 'lee')
print(musician)

# Jimi Hendrix
# John Lee Hooker
```
可选值让函数能够处理各种不同情形的同时，确保函数调用尽可能简单。

#### 返回字典
函数可返回任何类型的值，包括列表和字典等较复杂的数据结构。
```Python
def build_person(first_name, last_name, age=''):
    person = {'first': first_name, 'last': last_name}
    if age:
        person['age'] = age
    return person

musician = build_person('jimi', 'hendrix', age=27)
print(musician)
```
在函数定义中，我们新增了一个可选形参age，并将其默认值设置为空字符串。如果函数调用中包含这个形参的值，这个值将存储到字典中。在任何情况下，这个函数都会存储人的姓名，但可对其进行修改，使其也存储有关人的其他信息。

#### 结合使用函数和 while 循环
下面尝试使用名和姓跟用户打招呼：
```Python
def get_formatted_name(first_name, last_name):
    full_name = first_name + ' ' + last_name
    return full_name.title()

while True:
    print("\nPlease tell me your name:")
    print("(enter 'q' at any time to quit)")

    f_name = input("First name: ")
    if f_name == 'q':
        break

    l_name = input("Last name: ")
    if l_name == 'q':
        break

    formatted_name = get_formatted_name(f_name, l_name)
    print("\nHello, " + formatted_name + "!")

# Please tell me your name:
# (enter 'q' at any time to quit)
# First name: eric
# Last name: matthes

# Hello, Eric Matthes!

# Please tell me your name:
# (enter 'q' at any time to quit)
# First name: q
```

### 传递列表
假设有一个用户列表，我们要问候其中的每位用户。下面的示例将一个名字列表传递给一个名为`greet_users()`的函数，这个函数问候列表中的每个人：

