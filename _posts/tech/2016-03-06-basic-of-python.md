---
layout: post
title: Python学习之语法
category: 技术
keywords: Python
---
## Python学习之语法

## 数据类型

### 1.整数(int)
Python可以处理任意大小的整数,在程序中的表示方法和数学上的写法一样.

`1, 100, -8080, 0`

### 2.浮点数(float)
浮点数就是小数

`2.7788, 3.277`

### 3.字符串(str)
>3.1 字符串是以单引号或者双引号括起来的任意文本
 
    'hello', "my python",  "2+3"

注意：引号的使用与区别   

- 单引号中不能包含单引号;双引号不能包含双引号

            print("I'm ok")
		    I'm ok
- 单双引号交叉使用(单引号中使用双引号；双引号中使用单引号)

		print ('I"m ok')
		    I"m ok
>3.2 如果字符串内部即包含‘又包含“,可以用转义字符\来标识

        print 'It\'s a dog'  It's a dog;
        print 'I\'m \"OK\"!' I'm "OK"!


其他：\n #换行; \t #制表符

注意: 1) 字符\本身也要转义,\\即表示\;

2) 如果字符串里面有很多字符需要转义,需加很多\,为了简化,Python允许用r''表示''内部的字符串默认不转义

		   print (r'\\\t\\') 
		      \\\t\\

>3.3 三引号可以换行 '''...'''
>
     print ('''she is a 
	            ... beautiful girl''')
		she is a 
		beautiful girl	

### 4.布尔值(bool)	 
 
布尔值有True,False, 要么True,要么False

	    3>2  True ;
	    5<0  False

布尔值可以进行and,or,not运算

        True and True  True;
	    True or  False True;
		not True       False.

	
### 5.列表(list) 中括号哦

>5.1 Python中跟数组最接近的概念就是列表和元组,列表就是用来存储一连串元素的容器.

列表是一种有序的集合,可以随时添加和删除其中的元素.
 
	   classmates=['Michael','Bob','Lili']
	   len(classmates) #获取list的元素个数
>5.2 list的访问

用索引来访问list中的每个元素,索引位置从0开始 (还是中括号哦)

	 classmates[0] 'Michael';

如果取最后一个元素,可以用-1做索引,直接获取最后一个元素

	   classmates[-1] 'Lili'
	   classmates[-2] 'Bob'
	   
>5.3 list中元素追加
 list是一个可变的有序表,默认往list中追加元素都末尾.
	
        classmates.append("Lucy")
	    classmates.insert(1,'Jack') #将为元素插入到索引号1的位置
>5.4 删除list末尾的元素

        classmates.pop()
	    classmates.pop(1) #删除指定位置的元素 其中1指的是索引号为1
>5.5 替换元素

        classmates[1]='Sara'
	
  其他：list里面元素的数据类型也可以不同

	    L = ['Apple', 123, True]
		s = ['python', 'java', ['asp', 'php'], 'scheme']
   	
### 6. 元组(tuple) 括号哦

  元组里面的元素也是进行索引计算

  列表与元组的区别:

  1)列表里面的元素的值可以修改;元组里面的元素值不能修改;只能读取.
  2)列表与元组的符号不同

         classmates=('Michael','Bob','Lili');
	     classmats[0];
		 classmates[1]
当你定义一个tuple时,在定义的时候,tuple的元素就必须被确定下来.

    t = (1); t=(1,) #前者定义的不是tuple,是1这个数;后者定义只有1个元素的tuple.
		
其他：**'可变的'** tuple 

        t=('a','b',['A','B'])
        t[2][0]='X'
		t[2][1]='Y'
	    t=('a','b',['X','Y'])
指向列表的这一事实不变

### 7. 字典(dict) 大括号哦

 字典又叫关联数组,字典里面包含一整个事情,这个事情里面分包括各种方面的具体信息.

其使用键-值（key-value）存储,具有极快的查找速度.

	 zidian='name':'weiwei','home':'guilin','like':'music'}
          zidian['name']  
		  'weiwei';

    zidian['name']='wbxiaoxiao' #把数据放入dict的方法,除了初始化时指定外,还可以通过key放入
	{'home': 'guilin', 'name': 'wbxiaoxiao', 'like':'music'}

	'home' in zidian #通过in判断key是否存在
     True;

	 d.get('home',-1) #通过get方法判断key是否存在
    'guilin'

>7.1 删除一个key,对应的value也会从dict中删除
	   
    zidian.pop('home')
	{'name': 'weiwei', 'like': 'music'}
		 
其他:dict的特点 

 - 查找和插入的速度极快,不会随着key的增加而变慢
 - 需要占用大量的内存,内存浪费多
 
 list的特点  

- 查找和插入的时间随着元素的增加而增加
- 占用空间小,浪费内存很少

注意:	
			 
dict的key必须是不可变对象

    解释:通过key计算位置的算法成为哈希算法,保证hash的正确性,作为key的对象就不能变.字符串、整数等都是不可变的,可以作为key;list是可变的,不能作为key

			  key=[1,2,3]
			  d[key]='a list'
	               错误的
### 8. 集合(set)

集合两个功能,一个功能是建立关系,另一个功能是消除重复元素

        set(元素)
	    s=set([1,2,3])
>8.1 add(key)可以添加元素到set中
  
        s.add(4)
>8.2 remove(key)方法可以删除元素
       	 
        s.remove(4)
>8.3 set作交集,并集,差集等操作
	        
            s1&s2
		    s1|s2
	     	s1-s2
>8.4 消除重复元素

	        new=set(a)
注意:对于不变对象来说,调用对象自身的任意方法,也不会改变该对象自身的内容.相反,这些方法会创建新的对象并返回,这样,就保证了不可变对象本身永远是不可变的.
 

## 变量

   Python中在程序运行时可以随着程序的运行更改的量称之为变量.
   Python中，'='是赋值语句,可以把任意数据类型赋值给变量,同一个变量可以反复赋值，而且可以是不同类型的变量
   
## 常量	

Python中的程序运行时不会被更改的量称之为常量;常量的特点是'一旦绑定,无法更改'

## 行与缩进

逻辑行与物理行,Python中逻辑行主要是指一段代码,在意义上的行数;物理行时实际看到中的行数.

          #以下是3个物理行
          print "abc"
          print  "789"
          print  "777"

        #以下是1个物理行，3个逻辑行     
          print "abc";  print  "789";    print  "777"

        #以下是1个逻辑行，3个物理行
          print ''' 这里是
                极客学院
                提供的Python教程'''
   行中分号使用规则

Python中一个物理行一般可以包含多个逻辑行,在一个物理行中,逻辑行与逻辑行之间用分号隔开

每个逻辑行的后面必须跟分号;最后一个逻辑行的分号可以省略.

   行连接

多个逻辑行可以写在一个物理行中,如何将一个逻辑行分别写在多个物理行中.可以使用行连接符

           print "我们都是\
                     好孩子”
   缩进
 
        1. 一般情况下逻辑行首不应该出现空白
        2. if语句的缩进方法
        3. while循环的缩进方法
         
      缩进的方法有两种，可以按空格或者一个tab键

## 注释
    #解释代码的功能
       eg: print(s) # 打印出s

## 条件判断

 根据Python的缩进规则,如果if语句判断是True,就把缩进语句块执行了,否则,什么也不做.

        age=20
	    if age>=18:
			print('your age is',age)
			print('adult')
		('your age is', 20)
		adult	

可以给if添加一个else语句,意思是,如果if判断是False,不要执行if的内容,去把else执行了.

       age = 3
       if age >= 18:
			print('your age is', age)
			print('adult')
	   else:
			print('your age is', age)
			print('teenager')

可以用elif做更细致的判断

	   age = 3
	   if age >= 18:
			print('adult')
	   elif age >= 6:
			print('teenager')
	   else:
			print('kid')

if语句的完整形式：

    if <条件判断1>:
       <执行1>
    elif <条件判断2>:
       <执行2>
    elif <条件判断3>:
       <执行3>
    else:
       <执行4>  

注意:**if语句是从上往下判断,如果在某个判断上是True,把对应的语句执行后，就忽略掉剩下的elif和else.**
	  
## 循环
for...in循环,依次把list或tuple中的每个元素迭代出来.

	    names=['Michael','Bob','Lili']
	    for name in names 
			print(name) 
  
while循环,只要条件满足,就不断循环,条不满足时退出循环	
	
	   sum = 0
	   n=99
	   while n > 0:
			sum = sum + n
			n = n - 2
	   print(sum)
	
	
参考：[Python教程](http://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)

