# Dart

## 基础</br>
* [强类型](#强类型)
* [弱类型](#弱类型)
* [字符串打印](#字符串打印)
* [常量](#常量)
* [集合](#集合)



### 强类型
int、double、num、String、bool,初始默认类型都是null
```dart
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
```dart
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
```dart
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

### 集合
```dart
//1、Map
//Map定义
var map = <String,dynamic>{
  'name':"张三",
  "age":12
};
print("打印：$map")；//打印：{name: 张三, age: 12}

//Map转换成Json
var jsonStr = jsonEncode(map); //jsonEncode方法需要导包：import 'dart:convert';
print("打印：$jsonStr"); //打印：{"name":"张三","age":12}

//遍历方式
//forEach遍历
map.forEach((k,v){
  print("key：$k    value：$v");
});
//遍历所有Key
map.keys.forEach((k){
 print("key：$k");
});
//遍历所有value
map.values.forEach((v){
 print("value：$v");
});

//赋值
//1、根据Key来赋值
map["age"] = 56; //Key如果存在，则直接修改value的值，否则就创建一个新的key并且赋值。
//2、添加新元素，给不存在的key赋值，存在者不会赋值
Map<String, int> map1 = {'Bob': 36};
//方式一
map1.putIfAbsent("sex1", (){
    55;
});
//打印结果：sex1：null
//方式二
map1.putIfAbsent("sex2", ()=>66);
map1.putIfAbsent("sex2", ()=>77);
//打印结果：sex2:66    存在则不会赋值
//3、addAll赋值
//两个Map的value类型不同，可以赋值；
Map<String, dynamic> map1 = {"name": "张三"};
Map<String, int> map2 = {"age": 36};
map1.addAll(map2); //可以赋值
//Map中k和v如果类型已经确定，则无法赋值
Map<String, String> map1 = {"name": "张三"};
Map<String, int> map2 = {"age": 36};
map1.addAll(map2); //报错
```

```dart
//1、List
//定义
//(1)
List<dynamic> list = new List();
list.add(1);
list.add("sa");
//(2)
List<dynamic> list2 = [1,"sa"];
//(3)
var list = [1,"sa"];

//遍历
var list = [1,"sa"];
//forEach
list.forEach((v){
  print(v);
});
//for
for(var v in list){
  print(v);
}

//元素操作
var list = [1,"sa"];
//添加
list.add(2); //单个添加
list..add(3)..add("sa"); //链式添加
//删除
list.remove(2); //删除元素
list.removeAt(0); //删除元素索引



```

