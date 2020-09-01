# ssymoon.github.io# python数据分析

## python第一课

### 列表的建立


```python
int_list=[1,2,3,4,5] #整数型
str_list=["a","b","c","d","e"]#字符串
float_list=[1.0,2.0,3.0,4.0,5.0]#浮点型

print(*int_list,sep=',')#列表转换成参数，并用‘，’隔开
print(*str_list,sep=',')
print(*float_list,sep=',')

print(*str_list[2:],sep=',')#对结果进行切片

```

    1,2,3,4,5
    a,b,c,d,d
    1.0,2.0,3.0,4.0,5.0
    c,d,d
    

### 各种列表的处理


```python
int_list=[1,2,3,4,5] #整数型
str_list=["a","b","c","d","e"]#字符串
float_list=[1.0,2.0,3.0,4.0,5.0]#浮点型

合并：
    int_list.extend(str_list) #将str列表合并到int_list中
    int_list+str_list #将str列表合并到int_list中
插入
    int_list.insert(1,4) #在int_list列表的第2项后面插入整数4
删除
   int_list.pop(1) #在列表int_list中删除第2个值 
   int_list.remove(1) #在列表int_list中删除所有的整数1
索引
   int_list[1] #在列表int_list中获取第2项
   int_list[1:3] #在列表int_list中获取第2-4项
   int_list[1:] #在列表int_list中获取第2-最后
统计
   int_list.count(1) #统计int_list列表中1出现的次数
位置
   int_list.index(1) #统计int_list列表中1所在的位置数
 
```

### 字典的使用


```python
test_dict{} #建立一个空的字典
test_dict={'张三':12321321312,'李四':1232112313,'王五':12321321321,'老七':123212132112} #给test_dict字典增加key和value
test_dict #输出结果
```

### 输入输出填充

1、一对一填充
  print（'我喜欢吃{}'.format('牛肉')）#输出我喜欢吃牛肉

2、多对多填充
  print('我{}吃{}'.format('喜欢','牛肉')) #输出我喜欢吃牛肉

3、浮点数填充
  print('我的{}:{:.2f}'.format('身高',1.89876)) #{:.2f}表示变量四舍五入2位小数，3f表示3位小数
                                 输出结果：我的身高：1.90

### 缩进

所有的条件语句、函数、循环语句，结果都需要缩进

例子：
   a=2
   b=1
   if a>b
     print('a比b大')

### 循环


```python
#while循环
i=1
while i<=7:
    print("我已经学习{}天了".format(i))
    i+=1
print("我已经学习{}天啦，可以去找工作啦".format(i-1))

#for循环
m=[1,2,3,4,5]
for a in m:
   print(a)


```

    我已经学习1天了
    我已经学习2天了
    我已经学习3天了
    我已经学习4天了
    我已经学习5天了
    我已经学习6天了
    我已经学习7天了
    我已经学习7天啦，可以去找工作啦
    1
    2
    3
    4
    5
    

### 函数

#### 普通函数


```python
#规则 def 函数名（参数）
          语句块
#实际参数
def X(a):#声明函数
     print("我正在学习{}".format(a))#语句转换
X("吉他")#调用函数
X("钢琴")#调用函数

#形式参数
def Y(b):
    n=("这是一个{}".format(b))
    return n
Y("苹果")

#多个形式参数
def Z(c,d):
    m=("我正在用{}{}".format(c,d))
    return m#调用函数
Z("小米10","拍照")
    
```

    我正在学习吉他
    我正在学习钢琴
    




    '我正在用小米10拍照'



#### 匿名函数


```python
#规则 lambda arg1，arg2，arg3，...:expression
      #arg1表示参数，expression表示执行的操作
f=lambda x,y:x+y
f(1,2)#调用函数
```




    3



### 列表生成式

#### 将列表每个数平方输出


```python

#传统方法
i=[1,2,3,4.5]
m=[] #创建空的列表容器
for a in i:
    m.append(a**2)# "**"表示指数
m #s输出

#表达式
x=[1,2,3,4,5]
[i**2 for i in x]


```




    [1, 4, 9, 16, 25]



#### 将两个列表依次两两合并


```python
#传统方法

i=["1","2","3","4","5"]
m=["a","b","c","d"]
n=[]
for x in i:
    for y in m:
        n.append(x+y)
n
```




    ['1a',
     '1b',
     '1c',
     '1d',
     '2a',
     '2b',
     '2c',
     '2d',
     '3a',
     '3b',
     '3c',
     '3d',
     '4a',
     '4b',
     '4c',
     '4d',
     '5a',
     '5b',
     '5c',
     '5d']




```python
#表达式
a=[1,2,3,4,5]
b=[2,3,4,5,6]
[m+n for m in a for n in b]
```




    [3, 4, 5, 6, 7, 4, 5, 6, 7, 8, 5, 6, 7, 8, 9, 6, 7, 8, 9, 10, 7, 8, 9, 10, 11]



### map函数


```python
#描述：map(function,args) 表示对序列中每一个值进行function操作，结果需要通过for循环或list出来
def i(x):
    return x*x
m=[1,2,3,4,5]
n=map(i,m)

print(list(n))
```

    [1, 4, 9, 16, 25]
    


```python
#用隐匿函数写单列表map
a=map(lambda x,y:x+y,[1,2,3],[1,2,3])
for i in a:
    print(i)

```

    2
    4
    6
    


```python
#用普通函数写多列表map
def f(x,y):
    return x+y
a=[1,2,3]
b=[3,2,1]
c=map(f,a,b)
print(list(c))#or for i in c  print(i)
```

    [4, 4, 4]
    
