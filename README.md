# Dart

## 数据定义类型</br>
* [强类型](#强类型)
* [弱类型](#弱类型)
* [字符串打印](#字符串打印)
* [常量](#常量)



### 强类型
int、double、num、String、bool,初始默认类型都是null
```java
int a1 = 12;
double a2 = 12.5;
nul a3 = 13;
bool = true;
print("$a2 is test");
````


### 弱类型
var、dynamic、Object，初始默认类型都是null
区别:
* var：类型一但确定，就无法修改类型，不然回报错
* dynamic:类型确定，也可以修改
* Object:和dynamic差不多


### 字符串打印
```java
//$s 字符串占位符
int a1 = 1;
int a2 = 2;
print("$a2 is test $a1");

//字符串拼接
//第一种：字符串拼接方式
String s1 = "a" + "b";
//第二种：字符串自动拼接
String s2 = 'aa'   'bb';
//第三种：字符串模板打印
String s3 = 
"""
 abcd
  efg
""";

//字符串换行
//“\n”换行符
String s4 = "abc \n def";
//过滤特需字符
//字符串前面添加“r”，将过滤字符串中转义符，变为普通字符串
String s5 = r"abc \n def";

//String字符串都存放在常量池中，复用
String s1 = "a";
String s2 = s1 + "b";
String s3 = "ab";
s2 == s3; //true
```

### 常量
```java
//final关键字：一旦赋值，则不可修改；特性：不可变性可传递 
final String str = "aa";
str = "bb"; //报错

//特性：不可变性可传递
//类型不变，里面元素可发送改变
final str = [1,2,3,4];
str[1] = 5;//可以改变数值

//特点：赋值之后就不可修改，运行时确定
final DateTime currentDateTime =DateTime.now();


//const关键字：传递不可变行，影响子元素的可变性
const con = [1,2,3];
con[1] = 5; //报错，不能修改元素，但final可以修改

//const定义的变量，如果在内存中以存在，则复用
const c1 = [1,2,3];
const c2 = [1,2,3];
identical(c1,c2) //true

//特点：赋值必须明确
const PI = 3.1415926;
```



