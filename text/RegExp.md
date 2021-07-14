# 正则表达式   ( regular expression )
用于定义一些字符串的规则，计算机可以根据正则表达式，来检查一个字符串是否符合规则，或者将字符串中符合规则的内容提取出来

## 创建正则表达式的对象
    语法：
        
        var 变量 = new RegExp('正则表达式','匹配模式')
        
        使用typeof检查正则对象，会返回object 
        
        var reg = new RegExp('a'); 这个正则表达式可以用来检查一个字符串中是否有a

        在构造函数中，可以传递一个匹配模式，作为第二个参数
        
            i 忽略大小写
            
            g 全局匹配
            
            m 换行匹配

## 正则表达式的方法
    test()

        使用这个方法，可以用来检查一个字符串，是否符合正则表达式的规则

        如果符合返回true，不符合返回false

## 使用字面量来创建正则表达式
    语法：
    
        var 变量 = /正则表达式/匹配模式
            
            使用字面量的方式创建更加简单
            
            使用构造函数创建更加灵活 

### 创建一个正则表达式，检查一个字符串
    [a-z] 任意的小写字母

    [A-Z] 任意的大写字母 

    [A-z] 任意字母

    [0-9] 任意数字

    [^ab] 除了ab之外的任何字符

    使用 | 表示或者的意思
        
    []里的内容也是或的意思
        
    [abc] == a|b|c

    \w     任意字母，数字，_   [A-z0-9_]

    \W     除了字母，数字，_   [^A-z0-9_]

    \d     任意数字     [0-9]

    \D     除了数字     [^0-9] 

    \s     空格       

    \S     除了空格

    \b     单词边界 

    \B     除了单词边界

### 量词    
    
    通过量词可以设置一个内容出现的次数，只对它前边的一个内容起作用

    {n} 刚好出现n次

    {m,n} 出现m--n次

    {m,} 出现m次以上

    x+  至少一个x  相当于{1,}

    x*  0个或多个x  相当于{0,}

    x?  0个或一个x  相当于{0,1}

    ^x  表示以x开头

    x$  表示以x结尾

    ^x$  表示这个字符串就是'x'

### 检查一个字符串中是否含有 .

    . 表示任意字符

    在正则表达式中，使用\作为转义字符

    \.  表示.

    \\  表示\

    使用构造函数时，由于它的参数是一个字符串，而\是字符串中的转义字符

    如果需要使用\，则需要用\\来代替

# 字符串的方法

### search()   

    可以搜索字符串中是否含有指定内容 

    如果搜索到指定内容，则会返回第一次出现的索引，没有则返回-1

    可以接受一个正则表达式作为参数，然后根据正则表达式去检索字符串

    只会查找第一个，设置全局匹配也没用

### match()

    可以根据正则表达式，从一个字符串中将符合条件的内容提取出来

    默认情况下的match只会找到第一个符合要求的内容，找到以后就停止检索

        可以设置正则表达式为全局匹配模式，就可以匹配到所有的内容

        可以为一个正则表达式设置多个匹配模式，顺序无所谓

    match()会将匹配到的内容封装到一个数组中返回

### replace()
    
    可以将字符串中指定内容替换为新的内容

    参数：

        第一个，被替换的内容，可以接收一个正则表达式作为参数

        第二个，新的内容
    
    默认只会替换第一个

### split() 

    可以将一个字符串拆分为一个数组

    参数

        需要一个字符串作为参数，会根据该字符串拆分

        如果传递一个空串作为参数，则会将每个字符都拆分为数组中的一个元素

### slice()  

    可以从字符串中截取指定的内容，不会影响原字符串，而是将截取到的内容返回

    参数：

        第一个，开始位置的索引(包含开始位置)

        第二个，结束位置的索引(不包含结束位置)

            如果省略第二个参数，则会截取到后边所有的

        也可以传递一个负数作为参数，负数是从后边计算

### substring()   
    用来截取一个字符串，跟slice()类似

    参数：

        第一个，开始位置的索引(包含开始位置)

        第二个，结束位置的索引(不包含结束位置)

        不接受负值作为参数，如果传递负值，则默认使用0

        还会自动调整参数的位置，如果第二个参数小于第一个，则自动交换

### substr()   
    用来截取字符串

    参数：

        第一个，开始位置的索引
        
        第二个，截取的长度

### indexOf()   
    可以检索一个字符串中是否含有指定内容

    如果字符串中含有该内容，则会返回第一次出现的索引

    如果没有找到指定的内容，则返回 -1

    可以指定一个第二参数，指定开始查的位置

### lastIndexOf():
    用法和 indexOf() 一样

    indexOf 是从前往后找

    lastIndexOf 是从后往前找 

    也可以指定开始查找的位置  

### concat()   
可以用来连接两个或多个字符串

### toUpperCase()	
把字符串转换为大写并返回

### toLowerCase()	
把字符串转换为小写并返回

### charAt()   
可以返回字符串中指定位置的字符，根据索引获取指定的字符

### charCodeAt()   
获取指定位置字符的字符编码(Unicode编码)

### String.formCharCode()   
可以根据字符编码去获取字符

     

     

                