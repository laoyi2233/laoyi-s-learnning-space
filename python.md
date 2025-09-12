# 变量与运算    
变量  
打印  
数学运算  
 '+'	加	3+4=7  
 '-'	减	3-4=-1  
 '*'	乘	3*4=12  
 '/'	除	3/2=1.5  
 '%'	取模	103%100=3  
  **	幂	3**2=9  
 '//'	取整除	10//3=3  


# 条件判断 
if
if—else 如果否则

判断	含义  
a == b	a 是否等于 b  
a > b	a 是否大于 b  
a >= b	a 是否大于等于 b  
a < b	a 是否小于 b  
a <= b	a 是否小于等于 b  
a != b	a 是否不等于 b  


True and True	需要两边同时满足才能返回 True  
True or False	只要一边是 True 则返回 True  
not True	给出相反结果  

if-elif-else  
today = 4  
if today == 1:  
    print("周一")  
elif today == 2:  
    print("周二")  
elif today == 3:  
    print("周三")  
else:  
    print("周一周二周三之外的一天")    
# 循环  
for循环  
for i in range(a,b,c) a到b，步长为c  

while循环  
    	  特点  
for	    天然适合在有限的循环中  
while 	可以被用在无限循环中  
脑海中想到的是要处理一个一开始就有明确长度的序列，那么你第一个想到的应该是 for 循环。
如果你脑海中这个序列你不知道要在什么时候停，或者它是无限长的一个序列，或者运行无限次数，
那你第一个想到的应该要用 while 循环。  


guess_num = 10  
while guess_num != 20:  
    guess_num += 1  
    print(guess_num)  

continue 跳过后面的函数，直接进入下一次循环  
break    结束循环  

# 数据种类
list  []  


dict  
files = {"ID": 111, "passport": "my passport", "books": [1,2,3]}  
print(files)  
print(files["books"])  

tuple元组  ()  


set合集  有着和集合类似的数学性质，唯一，无序


在循环中运用
上面这些，特别是列表和字典，是经常和循环一起用的，毕竟如果要手写对每一个元素的加工，那是一件相当复杂的工作。所以我们可以在循环中批量处理。 注意，下面的 len(files) 给出的是这个 files 列表的长度，我们常用在循环中。


files = ["f1.txt", "f2.txt", "f3.txt", "f4.txt", "f5.txt"]  
for i in range(len(files)):  
    if files[i] == "f3.txt":  
        print("I got f3.txt")  


其实还能再简化一些，直接将 files 放入循环里。这样我们就不需要再去索引一遍 files 而是直接将 files 里面的值在 for 的时候就一一拿出来了。  
files = ["f1.txt", "f2.txt", "f3.txt", "f4.txt", "f5.txt"]  
for f in files:  
    if f == "f3.txt":  
        print("I got f3.txt")  
​

同样，字典也能和 for 进行简化的应用。我们只需要调用 dict.items(), dict.keys(), dict.values() 分别取字典的某些部分就能简化 for 循环了。  
files = {"ID": 111, "passport": "my passport", "books": [1,2,3]}  
for key in files.keys():  
    print("key:", key)  
for value in files.values():  
    print("value:", value)  
for key, value in files.items():  
    print("key:", key, ", value:", value)  
​

自带功能
列表和字典远远还没有结束哦，他们的功能其实挺丰富的。和 for 一起循环，我们来演示一下常用的一些列表，字典的功能函数吧。 第一个要介绍的是怎么往列表里面添加和pop值。  
files = []  
for i in range(5):  
    files.append("f"+str(i)+".txt")  
    print("has", files)  
for i in range(len(files)):  
    print("pop", files.pop())   
    print("remain", files)  

当然还有很多，我们下面一一举一些比较常用的功能。  
files = ["f1.txt", "f2.txt"]  #扩充入另一个列表  
files.extend(["f3.txt", "f4.txt"])  
print("extend", files)  #按位置添加
files.insert(1, "file5.txt")     #添加入第1位（首位是0哦）  
print("insert", files)  #移除某索引  
del files[1]  
print("del", files)  #移除某值   
files.remove("f3.txt")  
print("remove", files)  
​

字典也是，也有额外的一些常用功能，比如get(), update()等，我下面在补充一下。  
files = {"ID": 111, "passport": "my passport", "books": [1,2,3]}  
#按key拿取，并在拿取失败的时候给一个设定好的默认值  
print('files["ID"]:', files["ID"])  
print('files.get("ID"):', files.get("unknown ID", "不存在这个 ID"))  

#将另一个字典补充到当前字典  
files.update({"files": ["1", "2"]})  
print('update:', files)  

#pop 调一个item，和列表的 pop 类似  
popped = files.pop("ID")  
print('popped:', popped)  
print("remain:", files)  
files = {"ID": 111, "passport": "my passport", "books": [1,2,3]}  
#按key拿取，并在拿取失败的时候给一个设定好的默认值  
print('files["ID"]:', files["ID"])  
print('files.get("ID"):', files.get("unknown ID", "不存在这个 ID"))  
#将另一个字典补充到当前字典  
files.update({"files": ["1", "2"]})  
print('update:', files)  
#pop 调一个item，和列表的 pop 类似  
popped = files.pop("ID")  
print('popped:', popped)  
print("remain:", files)  


# 函数  
class类  
模块  
读写文件  
文件目录管理  
正则化表达  
pickle/json序列化  
控制异常try—except  
单元测试  
