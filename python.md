# 变量与运算    
变量  
打印  
数学运算  
 `+`	加	3+4=7  
 `-`	减	3-4=-1  
 `*`	乘	3*4=12  
 `/`	除	3/2=1.5  
 `%`	取余数	103%100=3  
 `**`	幂	3**2=9  
 `//`	取整除	10//3=3  


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
def() 定义函数  
retun 返回函数的运算结果  
参数设置 忽略参数名，按顺序传参，如有参数名，可打乱顺序按参数名穿参  


全局变量与局部变量  
变量	特点  
全局 global	函数里外都能用 （公用）  
局部 local	仅在函数内有用 （私有）  


def modify_name():  
    filename = "f1.txt"  
    print("local filename:", filename)  
modify_name()  
print("global filename:", filename) #这里会报错  


那么如果这个 filename 是公用的，每一个函数都能获取到的，我们怎么定义呢？ 其实你就把 filename 拎出来，放到外面就好了。  
filename = "f1.txt"  
def modify_name():  
    print("local filename:", filename)  
modify_name()  
print("global filename:", filename)  


自私的 modify_name() 想自己在内部搞一套标准， 你外面有啥不要紧，如果我自己也搞一个一样的东西，那我就觉得自己这个更重要，就不看外面的东西了。所以local的filename就是 modify_name() 自己那一套。  
filename = "f1.txt"  
def modify_name():  
    filename = "f2.txt"  
    print("local filename:", filename)  
modify_name()  
print("global filename:", filename)  


存在另一种情况，就是允许内部来修改外部的值。为了办这件事，modify_name() 必须先向外面打一个申请报告，向外面申请自己要去修改公用的 filename。  
filename = "f1.txt"  
def modify_name():  
    global filename  #提出申请  
    filename = "f2.txt"  
    print("local filename:", filename)  
modify_name()  
print("global filename:", filename)   

# class类  
用 **class File**来创建一个大概念（类），注意我们通常约定类的名字要首字母大写。 然后用 **my_file = File()** 来创建一个具体的文件。 每个具体的个体都带有这个类的基本属性，如 create_time, name。就像每个人都会有人类这个类当中的性别，年龄一样。


class File:  
    def `__init__`(self):  
        self.name = "f1"  
        self.create_time = "today"  
my_file = File()  
print(my_file.name)  
print(my_file.create_time)  


**self** 是作为类自己的一个索引，不管你在定义类的时候，想要获取这个类的什么属性或功能，都可以通过 self 来获取。 比如这个 File 类中，获取类自己的 create_time，就写成了self.create_time。之后在说类的功能的时候， 也是通过 self 来在类内部调用的。  


什么是**`__init__`**每当你进行一次 my_file = File() 这种操作的时候，把类给实例化的时候， File 类都会触发一次 `__init__` 功能，所以这是一个功能，用于初始化一些设置。


类似字典，字典的索引是key，而在class中索引是用文件名+.xx来实现的，.xx就可以调用到储存在这个索引下的信息。我明白class类的含义了，我们要赋予一批变量许多的不同类型的特征，这些特征是这些变量共有的，为了方便，我们可以先将这些特征给提取出来，需要赋值的特征此后直接赋就行了，一些不需要赋值的特征则是该类都相同的特征，想要调用这些特征就利用索引。  


class Dog:  
    def `__init__`(self, name, age):  
        self.name = name  #属性  
        self.age = age  
    def bark(self):      #方法    
        print(f"{self.name} says: Woof!")   
#创建对象  
my_dog = Dog("Buddy", 3)  
my_dog.bark()  #输出: Buddy says: Woof!  


这里的狗叫就是所有狗都会有的共同特征，可以直接调用，不要赋值。  
class的功能可以通过字典与函数来模拟，但class更加方便且有独特功能。  

### 继承
比如我有定义文本文件和视频文件，如果分开定义两个类，我可以这样写：  


class Video:  
    def `__init__`(self, name, window_size=(1080, 720)):  
        self.name = name  
        self.window_size = window_size   
        self.create_time = "today"   
class Text:  
    def `__init__`(self, name, language="zh-cn"):   
        self.name = name   
        self.language = language   
        self.create_time = "today"    


这两种文件，其实是有共性的，比如他们都有 name，说到这里，我突然意识到，其实他们还可以抽象出一个更底层的类，也就是文件类。这个文件类包含了属于文件所具备的共同属性和功能。 我们可以通过继承的方式，将细分类嵌入到抽象类中，减少共有属性/功能的重复开发。  


class File:  
    def `__`init`__`(self, name, create_time="today"):  
        self.name = name  
        self.create_time = create_time  
    def get_info(self):  
        return self.name + "is created at" + self.create_time  
class Video(File):  # 继承了 File 的属性和功能  
    def `__`init`__`(self, name, window_size=(1080, 720)):  
        #将共用属性的设置导入 File 父类  
        super().`__`init`__`(name=name, create_time="today")  
        self.window_size = window_size  
class Text(File): # 继承了 File 的属性和功能  
    def `__`init`__`(self, name, language="zh-cn"):  
        # 将共用属性的设置导入 File 父类  
        super().`__init__`(name=name, create_time="today")  
        self.language = language 
        
#这里name=name第一个name是函数中的neme，即变量name，create_time="today"，ceate_time是指父类中该函数作为变量的变量名，today则是对该变量进行的赋值，在赋值后调用变量名就可以调用该特征。  
        
        
#也可以在子类里复用父类功能  
    def get_more_info(self):  
        return self.get_info() + ", using language of " + self.language  
v = Video("my_video")  
t = Text("my_text")   
print(v.get_info())     #调用父类的功能  
print(t.create_time)    #调用父类的属性  
print(t.language)       #调用自己的属性  
print(t.get_more_info()) #调用自己加工父类的功能   


**继承**同时继承父类中函数里的参数，如需修改，在子类调用父类中的函数时输入对应的参数值即可。


### 私有属性和功能  


class File:  
    def `__`init`__`(self):  
        self.name = "f1"  
        self.`__`deleted = False  #我不让别人用这个变量  
        self.`_`type = "txt"      #我不想别人使用这个变量  
    def delete(self):  
        self.`__`force`_`delete()      
    def `__`force`_`delete(self):  #我不让别人使用这个功能  
        self.`__`deleted = True  
        return True       
    def `_`soft`_`delete(self):     #我不想让别人使用这个功能   
        self.`__`force_delete()   #我自己可以在内部随便调用   
        return True  
f = File()  
print(f.`_`type)      #可以拿到值，但是这个类的作者不想让你直接这样拿到  
print(f.`_`soft_delete())  #可以调用，但是这个类的作者不想让你直接调用  

#接下来的两个实验都会报错  
#f.`__`deleted  
#f.`__`force_delete()  
txt  
True  


为什么会有上面的实验现象呢？其实这种私有属性的东西，通常是你为别人开发项目的时候才要考虑的。 有的属性或者功能，你不需要让别人知道，也不需要让别人调用，纯属自己开发时才会用到的一些东西， 所以就可以用私有化，强隐藏或者弱隐藏起来。  

 
`_`   ：  一个下划线开头	弱隐藏 不想让别人用 （别人在必要情况下还是可以用的）Python 遵循 ​​“我们都是成年人”​​ 原则：单下划线 `_`xx仅是约定，​信任开发者会遵守规范。如果你强行访问f.`_`type，Python 不会阻止，但作者可能在未来版本中修改它，导致你的代码崩溃。  


`__` ：  两个下划线开头	强隐藏 不让别人用  


### 魔术方法  
1. 魔术方法的真正价值


（1）赋予对象“原生行为”  
魔术方法让自定义对象能像 Python 内置类型（如 list、str、int）一样工作：  
示例：实现 `__add__` 后，你的对象支持 `+` 操作符。  


  class Vector:  
      def `__init__`(self, x, y):  
          self.x = x  
          self.y = y  
      def `__add__`(self, other):  
          return Vector(self.x + other.x, self.y + other.y)  
  v1 = Vector(1, 2)  
  v2 = Vector(3, 4)  
  v3 = v1 + v2  #调用 `__add__`，而非普通方法  

  
  如果没有 `__add__`：你只能写 v1.add(v2)，违背 Python 的直观语法。  

  
（2）无缝集成 Python 生态系统  
许多 Python 内置函数和语法依赖魔术方法：
len(obj) → 调用 obj.`__len__`()  
iter(obj) → 调用 obj.`__iter__()`  
with open(...) as f: → 依赖 `__enter__` 和 `__exit__`  
for x in obj: → 依赖 `__iter__` 或 `__getitem__`    
如果不用魔术方法：你的类无法兼容这些标准接口！   


3. 实际场景对比  
场景：比较两个对象  


❌ 不用魔术方法（臃肿）  


class Person:  


    def `__init__`(self, age):  
        self.age = age  
    
    def is_older_than(self, other):  
        return self.age > other.age  

p1 = Person(20)  
p2 = Person(30)  
p1.is_older_than(p2)  #必须显式调用方法  


✅ 用魔术方法 `__gt__`（直观）  


class Person:  


    def `__init__`(self, age):  
        self.age = age  
    
    def `__gt__`(self, other):  
        return self.age > other.age  

p1 = Person(20)  
p2 = Person(30)  
p1 > p2  #直接使用 > 操作符  


# 模块 module  
module与class有点像  
`__init__``.py这个文件在引用模块时会自动运行，起到了初始化模块的作用    


# 读写文件  
### 创建文件  


f = open("new_file.txt", "w")   #创建并打开  
f.write("some text...")         # 在文件里写东西  
f.close()                       # 关闭  


如果你觉得要写一个 f.close() 或者有时候你怕自己忘记要 close(), Python 人性化地提供了另外一种打开文件的方式。这个方式把打开和关闭嵌入到了一个 with 架构中。所以再也不用担心忘记关闭文件了，这种with的模式也是我个人比较喜欢的模式。下面这个案例，除了使用了with模式，我还换了一种写入数据的方式writelines()，当你传入像列表样的数据时，列表中的每个元素就是一行记录，数据会分行来写。


with open("new_file2.txt", "w") as f:  
    f.writelines(["some text for file2...\n", "2nd line\n"])  

    
### 读文件  
在读文件的时候，和写文件的方式是十分类似的，就把里面的w改成r。也就是说，其实w代表的是write，r代表的是read。  


f = open("new_file2.txt", "r")  
print(f.read())  
f.close()  


上面有演示如果你的记录是一个列表，你想在文件中每行记录列表当中的一个值，可以用 writelines()，那么在读文件的时候， 也可以 readlines() 直接读出来一个列表。


with open("new_file2.txt", "r") as f:  
    print(f.readlines())  


在机器学习和大数据的时代，我们的数据往往是非常大的，很多都是以GB为单位。而如果一次性读取一个这么大的文件，很有可能你的内存都放不下。 怎么办呢？我们能不能一行一行读取，取代一次性读取，不让内存被一次性占满？当然可以，readline() 就来拯救你了。 注意哦，这个功能没有 s，不是上一个功能哦。


with open("new_file2.txt", "r") as f:  
    while True:  
        line = f.readline()  
        print(line)  
        if not line:  
            break  


### 文件编码，中文乱码   
有些文件在 Windows 存储的时候，是以 gbk 的格式存储的，下面的 chinese.txt 我就模拟用 gbk 编码保存。 注意这里我选用的写模式 w 还多了一个 b，合起来是 wb，意思是 write binary 形式，取代默认的 text 形式。所以我读的时候， 也加上了一个 b，变成了 rb，read binary。  


with open("chinese.txt", "wb") as f:  
    f.write("这是中文的，this is Chinese".encode("gbk"))  

with open("chinese.txt", "rb", ) as f:  
    print(f.read())  
    #print(f.read().decode('gbk'))  # windows在本机尝试，可以试试这个  


怎么办？方法还是有的，我们先确认是哪一种文件编码，然后在读的时候，需要传入一个 encoding 的参数，表示用这一种编码来读。 这样中文乱码的问题就顺利解决了。  


with open("chinese.txt", "r", encoding="gbk") as f:  
    print(f.read())  


### 更多读写模式
mode	 意思  
w	   （创建）写文本  
r	    读文本，文件不存在会报错  
a	    在文本最后添加  
wb	   写二进制 binary  
rb   	读二进制 binary  
ab	   添加二进制  
w+	   又可以读又可以（创建）写  
r+	   又可以读又可以写, 文件不存在会报错  
a+	   可读写，在文本最后添加  
x	    创建  


举几个例子，体验一下。   
with open("new_file.txt", "r") as f:  
    print(f.read())   
with open("new_file.txt", "r+") as f:  
    f.write("text has been replaced")  
    f.seek(0)       #将开始读的位置从写入的最后位置调到开头  
    print(f.read())  


with open("new_file.txt", "a+") as f:   
    print(f.read())   
    f.write("\nadd new line")   
    f.seek(0)       #将开始读的位置从写入的最后位置调到开头   
    print(f.read())    


# 文件目录管理  

文件目录操作  
os.getcwd()  当前目录  
os.listdir()  当前目录里有什么  
os.makedirs()  创建一个文件夹  os.makedirs("project", exist_ok=True)    
os.path.exists()  检验是否存在该文件夹  
文件管理系统  
os.removedirs()  删除文件夹，但要求文件夹里没有文件  
shutil.rmtree()  删除文件夹里的文件  
os.rename()   改名字  
文件目录多种检验  
os.path.isfile()  检验文件是否存在  
os.path.exists()  检验文件或文件夹是否存在  
os.path.isdir()   检验目录是否存在  
os.path.basename()  拿到文件名  
os.path.dirname()  拿文件夹名   
os.path.split()  分割路径，提取路径，tail：文件名或最后一个路径，head：前面的所有路径。
os.path.join  拼接路径  


# 正则表达式
不用正则的判断  
re.compile()  
ptn.search()  


import re  
ptn = re.compile(r"\w+?@\w+?.com")  
matched = ptn.search(mofan@mofanpy.com)  
print("mofan@mofanpy.com is a valid email:", matched)  
matched = ptn.search("mofan@mofanpy+com")  
print("mofan@mofanpy+com is a valid email:", matched)   


span = (a,b)的含义，这表示我们要找的pattern在原始字符中是从a开始，b结束。  


match = re.search(r"run","i run to you")  
print(match)  
print(match.group())  


#运行结果  
<re.Match object; span=(2, 5), match='run'>  #注意空格也算作字符内，且第一个字符的序号为0，左闭右开  
run  


### 满足多种条件   
1.|或  
re.search(r"run|ran","i ran to you")  
#这个|表示两个都可以检验，但只检验第一次在文本中出现的字符  


2.[]  
re.research(r"r[au]n","i ran to you")  
#在[]内，只要是出现的字符都可以检验，不需要考虑到顺序  
re.search(r"[\u4e00-\u9fa5！？。，￥【】「」]+", "我爱莫烦。莫烦棒！")  
只有在找到‘。’后，才会继续找后面的中文，也就是说re.search匹配的方式其实是从第一个字符开始遍历到最后一个字符，当运行一次，第一次找到到第一次没找到，产生了一个区间后，就停止遍历，也就是说它指挥产生一个区间，也就是说只会出现一个span=(a,b)。  


3.|+()
re.search(r"f(ou|i)nd","i find you")  
re.search(r"f(ou|i)nd", "I found you")  
#此时在f之后，nd之前的字母既可以是ou，也可以是i。  


### 通用匹配方式
字符匹配  
\d	任何数字	[0-9]    
\D	非数字字符	  [^0-9]   
\w	任何大小写字母,数字和下划线_	[a-zA-Z0-9_]   
\W	非字母、数字、下划线_  [^\w]  	  
. 	匹配任何字符 (除了 \n)	  


空白字符  
\s	任何空白字符	[ \t\n\r\f\v]  
\S	空白字符以外的	[^\s]    


边界匹配(匹配=找)  
\b	匹配一个单词边界	比如 er\b 可以匹配 never 中的 er，但不能匹配 verb 中的 er  
\B	匹配非单词边界	比如 er\B 能匹配 verb 中的 er，但不能匹配 never 中的 er     
^	匹配一行的开头，在 re.M 下，每行开头都匹配	  
$	匹配一行的结尾，在 re.M 下，每行结尾都匹配	  
\A	匹配最开始，不受多行影响，在 re.M 下，也从文本最开始	  
\B	匹配最结尾，不受多行影响，在 re.M 下，也从文本最结尾	  


量词
?	前面的模式可有可无，0次或1次	  
*	前一个字符0次或多次	    
+	前一个字符1次或多次	   
{n,m}	重复 n 至 m 次	   
{n}	重复 n 次
{n,}  至少n次  
+?	非贪婪，最小方式匹配 +	   
*?	非贪婪，最小方式匹配 *	   
??	非贪婪，最小方式匹配 ?	  


分组与捕获   
( )  捕获分组   
(?: )  非捕获分组  
\1, \2   引用分组   


特殊转义  
\\  匹配字面的反斜杠  
\|  或操作   


字符集[]
[aeiou] 匹配任意元音字母  
[^aeiou] 匹配任意非元音字母  
[a-z]  匹配小写字母  
[0-9A-F]  匹配十六进制字符   
[\u4e00-\u9fa5]  匹配中文

标志  
re.I  忽略大小写  
re.M  多行模式（影响^和$)  
re.S  让.匹配换行符  
re.L  使预定字符类 \w \W \b \B \s \S 取决于当前区域设定  
re.U  使预定字符类 \w \W \b \B \s \S \d \D 取决于unicode定义的字符属性  
re.X  详细模式。这个模式下正则表达式可以是多行，忽略空白字符，并可以加入注释。以下两个正则表达式是等价的  


\w,+?的使用例子  
re.search(r"\w+?@\w+?.com","mofan@mofanpy.com")  


\d,{}的使用例子  
re.search(r"138\d{8}","13812345678")
re.search(r"138\d{8}","1234567890000")  


?,.*的使用例子
re.search(r"不？爱","我不爱你)
re.search(r"不？爱","我爱你")
re.search(r"不.*?爱","我不是很爱你")


正则表达式  
re.search()	扫描查找整个字符串，找到第一个模式匹配的  


re.match()	 从字符的最开头匹配，找到第一个模式匹配的即使用 re.M 多行匹配，也是从最最开头开始匹配	  


re.findall()	返回一个不重复的 pattern 的匹配列表	  


re.finditer()	和 findall 一样，只是用迭代器的方式使用	  


re.split()	用正则分开字符串  


re.sub()	用正则替换字符  


re.subn()	和 sub 一样，额外返回一个替代次数   


group的使用例子  
只要我们在正则表达中，加入一个 () 选定要截取返回的位置， 他就直接返回括号里的内容。  
string = "I have 2021-02-01.jpg, 2021-02-02.jpg, 2021-02-03.jpg"  
print("without ():", re.findall(r"[\w-]+?\.jpg", string))  
print("with ():", re.findall(r"([\w-]+?)\.jpg", string))  


那如果我想获取更详细的信息呢？比如年月日分开获取？答案是多做几个括号就好了，然后用 group 功能获取到不同括号中匹配到的字符串。  
string = "I have 2021-02-01.jpg, 2021-02-02.jpg, 2021-02-03.jpg"  
match = re.finditer(r"(\d+?)-(\d+?)-(\d+?)\.jpg", string)  
for file in match:   
    print("matched string:", file.group(0), ",year:", file.group(1), ", month:", file.group(2), ", day:", file.group(3))    
此中的group(0)指的是匹配到的完整的字符串  


下面这个 findall 也可以达到同样的目的。只是它没有提供 file.group(0) 这种全匹配的信息。  
string = "I have 2021-02-01.jpg, 2021-02-02.jpg, 2021-02-03.jpg"  
match = re.findall(r"(\d+?)-(\d+?)-(\d+?)\.jpg", string)  
for file in match:  
    print("year:", file[0], ", month:", file[1], ", day:", file[2])  
此函数不提供group(0)  


有时候我们 group 的信息太多了，括号写得太多，让人眼花缭乱怎么办？我们还能用一个名字来索引匹配好的字段， 然后用 group("索引") 的方式获取到对应的片段。注意，上面方案中的 findall 不提供名字索引的方法，也就是说findall只能用数字索引，我们可以用 search 或者 finditer 来调用 group 方法。为了索引，我们需要在括号中写上 **?P<索引名>** 这种模式。  
string = "I have 2021-02-01.jpg, 2021-02-02.jpg, 2021-02-03.jpg"  
match = re.finditer(r"(?P<y>\d+?)-(?P<m>\d+?)-(?P<d>\d+?)\.jpg", string)  
for file in match:  
    print("matched string:", file.group(0),   
        ", year:", file.group("y"),   
        ", month:", file.group("m"),   
        ", day:", file.group("d"))  














# pickle/json序列化  
控制异常try—except  
单元测试  
