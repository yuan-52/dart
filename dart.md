## Dart基础（一）
### 一、变量的声明
##### var 关键字：

######  &nbsp;  &nbsp;  var关键字声明的是一个不与要指定类型的变量，该变量在第一次赋值时类型就被确定，再无法修改类型。
<br/>

```
var str = '字符串类型';
str = 2;    ///err
```
##### final / const 关键字：

######  &nbsp;  &nbsp;  使用过程中从来不会修改的变量，final 变量的值只能被设置一次； const 变量在编译时就已经固定, const还可以用来创建常量值，以及声明创建常量值的构造函数。
<br/>

```
final str = '字符串类型';
str = '222';    ///err
```

##### dynamic / Object 关键字：

######  &nbsp;  &nbsp;  他们都可以声明一个可变类型的变量
<br/>

```
dynamic str = '字符串类型';
str = '222';    ///可以正常编译
```

### 二、变量的类型
#### Dart语言有以下几种类型： Number、 String、Boolean、 List(Array)、 Map、 Set、Symbol、 Rune(字符串中表示Unicode字符)
##### Number : 数字
###### &nbsp;&nbsp;int： 整数型，值不大于64位
###### &nbsp;&nbsp;double：  浮点数（小数），
##### String：字符串

``` 
String与Number的转换方法：
  var str = '1';
  var double1 = 3.1415926;
  var  int1 = 1;
  /// String -> int/double 
  int.parse(str);
  double.parse(str);
  /// int/double ->  String
  int1.toString() == str;       ///true
  double1.toStringAsFixed(2);
  double1.toStringAsFixed(2) == '3.14';        ///true
```
##### Boolean: 布尔值 
##### List: 集合
###### &nbsp;&nbsp; Dart中的List很像js中的array             &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; /// var list = [1,2,3,4];    list的长度与js中一样； 

```
list的方法：
1.使用List构造函数
var  list = List();   /var list = ['qq'];
2.在list里添加一个元素
list.add('cv');
3.在list里添加多个元素
list.addAll(['cv','ww']);
4.删除list中一个元素
list.removeAt(1);  ///下标
5.删除list中所有元素
list.clear();
3.在list里某个位置添加一个元素
list.insert(1, 'ee');
```

##### Map: 键值对集合（字典），map将key和value关联，以便于检索。在一个Map对象中key是唯一的，但value可以出现多次

```
Map的方法：
1.使用Map构造函数
var  searchMap = Map();   /指定Map中key和value的类型 var searchMap = Map<int, String>(); 
2.利用key检索value
var searchMap = {54: 'ceshi'};
search[54] == 'ceshi';     ///true
3.检查map中是否包含key
searchMap.containsKey(54);    ///判断结果是否为null;
4.移除一个key和value
searchMap.remove(54);
5.更多方法参考[Map](https://api.dart.dev/stable/2.13.4/dart-core/Map-class.html);
```
##### Set: 一个对象集合，每个对象只能出现一次。
```
1.使用Set构造函数
var inSet = Set();
2.
var names = <String>{};
var name = {'11','22','3'};
3.为Set添加元素：
names.add('00');
names.addAll(name);
4.移除Set中元素：
names.remove('11');
5.检查一个或多个元素是否在set中
names.contains('22');
names.containsAll(name);

6.更多方法参考[Set](https://api.dart.dev/stable/2.13.4/dart-core/Set-class.html);
```
##### Symbol: 标识符

### 三、运算符
#### 算数运算符
##### +  -  *  /  % （注意 / 结果是double , ~/ 结果才是int）
#### 关系运算符
##### 和js略不同， == 表示等于； !=表示不等于； > ; <; >=; <=
#### 类型判断运算符（as,  is,  is!）
```
注意 :使用 as 运算符将对象强制转换为特定类型
```
#### 条件表达式
```
?:     三目运算符   
??      /// a??b  (如果a为null,就返回b, 否则就返回a);
??=    /// a ??= 8 (如果a为null,则8就赋值给a，否则a保持不变);
..     级联运算符；
?.     /// 在不明确对象是否存在的情况下访问对象的成员.(
     var test = null;
     print(test?.name);    ///不会抛出异常
)
```
