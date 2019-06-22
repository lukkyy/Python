# Python
 ### 安装
  * [Windows下Python环境的安装（Anaconda+Jupyter notebook+Pycharm）](https://zhuanlan.zhihu.com/p/59027692)
 
### 基础知识
* 键盘输入输出
```Python
a_input=input()
print(a_input)
```
* 写文件
```Python
file=open('my_file.txt','w') #'w'=write 'a'=append     #打开文件，若没有文件会新建一个文件
file.write('eat apple')                                #写入文件      
file.close()                                           #关闭文件
```
* 读文件
```Python
file=open('my_file.txt','r') #'r'=read
content=file.read()
content=file.readlines()
print(content)
```
### while 和 for 循环

### if 判断

### 定义函数

### 定义class类
```Python
# 先定义
class Calculator:      # class类推荐以大写的形式定义
	name='Tom'
	price=18              #属性
	def add(self,x,y):    #功能/函数
		print(self.name)
		result=x+y
		print(result)
# 在调用类		
cal=Calculator()
print(cal.name)

#初始化class的变量
#__init__取自英文中initial 最初的意思
class Calculator:
    def __init__(self, name, price):
        self.nam = name
        self.pri = price
cal=Calculator('t',10)
print(cal.nam)
print(cal.pri)
...
t
10
...
# 设置属性的默认值, 直接在def里输入即可
def __init__(self,name,price,height=10,width=14,weight=16):
更改默认值 比如c.wi=17再输出c.wi就会把wi属性值更改为17
```

### 加载模块
模块就是在你 import 什么东西去python 脚本的时候会用到的.
 * 加载模块
 ```
 import numpy as np
 ```
 * 安装/卸载/更新模块
 ```
 pip install numpy   # 这是 python2+ 版本的用法
 pip3 install numpy   # 这是 python3+ 版本的用法
 pip3 uninstall numpy
 pip3 install -U numpy # 更新外部模块
 ```
### try except
```
try:
    file = open('eeee', 'r+')   #r+ read and add
except Exception as e:                   #Exception为默认函数
    print('there is no file named as eeeee')
    response = input('do you want to create a new file')
    if response =='y':
        file = open('eeee','w')
    else:
        pass
else:
    file.write('ssss')
file.close()
```
***
### 元组, 列表, 字典
* List，列表是一系列有序的数列
添加 
```python
  a = [1,2,3,4,1,1,-1]
  a.append(0)    # 在a的最后面追加一个0
  print(a)      # [1, 2, 3, 4, 1, 1, -1, 0]
```
在指定的地方插入项：
```python
a = [1,2,3,4,1,1,-1]
a.insert(1,0)     # 在位置 1处添加0
print(a)          # [1, 0, 2, 3, 4, 1, 1, -1]
```

删除项：
```python
a = [1,2,3,4,1,1,-1]
a.remove(2)         # 删除第一个出现值为2的项
print(a)
# [1, 3, 4, 1, 1, -1]
```
索引 
```python
a = [1,2,3,4,1,1,-1]
print(a[0])  # 显示列表a的第0位的值
# 1

print(a[-1]) # 显示列表a的最末位的值
# -1

print(a[0:3]) # 显示列表a的从第0位 到 第2位(第3位之前) 的所有项的值
# [1, 2, 3]

print(a[5:])  # 显示列表a的第5位及以后的所有项的值
# [1, -1]

print(a[-3:]) # 显示列表a的倒数第3位及以后的所有项的值
# [1, 1, -1]

打印列表中的某个值的索引(index): a.index
a = [1,2,3,4,1,1,-1]
print(a.index(2))     # 显示列表a中第一次出现的值为2的项的索引
# 1

统计列表中某值出现的次数：a.count
a = [4,1,2,3,4,1,1,-1]
print(a.count(-1))
# 1
```
List 排序 ：a.sort / a.sort(reverse=True)

```python
a = [4,1,2,3,4,1,1,-1]
a.sort() # 默认从小到大排序
print(a)
# [-1, 1, 1, 1, 2, 3, 4, 4]
a.sort(reverse=True) # 从大到小排序
print(a)
# [4, 4, 3, 2, 1, 1, 1, -1]
```
***

### 正则表达式 (Regular Expression) 
又称 RegEx, 是用来匹配字符的一种工具. 在一大串字符中寻找你需要的内容. 
它常被用在很多方面, 比如网页爬虫, 文稿整理, 数据筛选等. 
最简单的一个例子, 比如我需要爬取网页中每一页的标题. 而网页中的标题常常是这种形式.
<title>我是标题</ title>
