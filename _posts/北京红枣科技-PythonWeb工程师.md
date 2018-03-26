---
layout: post
title: 北京红枣科技-PythonWeb工程师
categories: 面试题
description: 北京红枣科技-PythonWeb工程师
keywords: 面试题
---
#### 1.``__new__``和``__init__``的区别？
- ``__new__``是一个静态方法,而``__init__``是一个实例方法.
- ``__new__``方法会返回一个创建的实例,而``__init__``什么都不返回.
- 只有在``__new__``返回一个cls的实例时后面的``__init__``才能被调用.
- 当创建一个新实例时调用``__new__``,初始化一个实例时用``__init__``.

#### 2. read和readline以及readlines的区别？
- read:读取整个文件
- readline： 读取下一行， 使用生成器方法
- readlines： 读取整个文件到一个迭代器以供我们遍历

#### 3.写一个函数，计算一个给定的日期是该年的第几天
```python
def count(year, month, day):
    count = 0
    # 判断该年是平年还是闰年
    if year % 400 == 0 or (year % 4 == 0 and year % 100 != 0):
        print('%d年是闰年，2月份有29天！' % year)
        li1 = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
        for i in range(month - 1):
            count += li1[i]
        return count + day
    else:
        print('%d年是平年，2月份有29天！' % year)
        li2 = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
        for i in range(month - 1):
            count += li2[i]
        return count + day


if __name__ == "__main__":
    year = int(input('请输入年份：'))
    month = int(input('请输入月份：'))
    day = int(input('请输入日期：'))
    count = count(year, month, day)
    print('%d年%d月%d日是今年的第%d天！' % (year, month, day, count))

```
#### 4.字典有那些常用的内置方法？
- cmp(dict1, dict2):比较两个字典元素。
- len(dict): 计算字典元素的个数，即键的总数。
- str(dict)：输出字典可打印的字符串表示。
- dict.clear(): 删除字典内所有的元素。
- dict.copy(): 返回一个字典的浅复制。
- dict.fromkeys(seq[,val]): 创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值。
- dict.get(key, default=None): 返回指定键的值，如果值不在字典中返回default值。
- dict.has_key(key): 如果键再字典dict中返回true，否则返回false。
- dict.items(): 以列表返回可遍历的(键、值)元祖数组。
- dict.keys(): 以列表返回一个字典所有的键。
- dict.setdefault(key, default=None): 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default。
- dict.update(dict2): 把字典dict2的键/值对更新到dict里。
- dict.values(): 以列表返回字典中所有的值。
- pop(key[,default]): 删除字典给定键key所对应的值，返回值为被删除的值，key值必须给出，否则，返回default的值。
- popitem(): 随机返回并删除字典中的一对键和值。

#### 5. 有两个磁盘文件A和B，各存放一行字母，要求把这两个文件中的信息合并(按字母顺序排列)，输出到一个新文件C中。
```python
f1 = open("A.txt")
f1_txt = f1.readline()
f2 = open("B.txt")
f2_txt = f2.readline()
f3_txt = f1_txt + f2_txt

f3_list = sorted(f3_txt)

for f3 in f3_list:
    with open("C.txt", "a+") as f:
        f.write(f3)
```
#### 6.实现用户登录，要求输错第一次则提醒“输错三次账户将被锁定”，输错第二次则提醒“已错误输入两次！”输错第三次则提示“当日拒绝再次登录！”
```python
count = 0    #计数器
username = "aaa"  #登录用户名
userpassword = "asd"   #登录密码
f = open("aaa.txt","r")
file_list = f.readlines()
f.close()
lock= []
name = input("登录用户名：")
for i in file_list:1
    line = i.strip("\n")
    lock.append(line)
if name in lock:
    print("你的账户已锁定，请联系管理员。")
else:
    if name == username:
    #如果密码连续输错了三次，锁定账号
        while count <3:
            password = input("登录密码：")
            if name == username and password == userpassword:
                print("欢迎%s!"%name)
                break
            else:
                print("账号和密码不匹配")
                count +=1
        else:
            print("对不起，您的账号连续输错三次密码已被锁定，请联系管理员。")
            f = open("aaa.txt","w+")
            li = ['%s'%username]
            f.writelines(li)
            f.close()
    else:
        print("用户名不存在，请输入正确的用户名。")
```
#### 7.有一个字符串开头和末尾都有空格，比如“   adabdw   ”,要求写一个函数把这个字符串的前后空格都去掉。
```python
def romve_spce(str):
    new_str = str.strip()

    return new_str

 new_str = romve_spce("    adanadnd   ")
 print(new_str)
```
#### 8. 如果当前的日期为20170130，要求写一个函数输出N天后的日期，(比如N为2，则输出20170201)。

```python

import datetime


def get_day(y,m,d,n):
    the_date =datetime.datetime(y,m,d)
    result_date = the_date + datetime.timedelta(days=n)
    d = result_date.strftime("%Y-%m-%d")
    return d


print(get_day(2018,3,25,1))
```

#### 9.数据库表A中有姓名fname的数据类型为varchar(20),要求使用SQL语句修改改字段的数据类型为nvarchar2(50)。

```
ALERT TABLE A MODIFY COLUMN fname nvarchar(50);  
```
#### 10.数据库表A中有姓名fname、年龄fage两个字段，要求使用SQL语句查出姓名重复的人的姓名和重复条数。
```
select name, count(*) from A group by fname;
```
























