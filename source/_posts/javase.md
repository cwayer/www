---
title: 面向对象特性：继承 封装 多态 抽象
date: 2019-07-12 22:29:09
tags:
---
面向对象特性：继承 封装 多态 抽象

基本数据类型：整型、浮点、字符、布尔

引用类型：String等

int范围：

```
1、java中int的取值范围为-2147483648到+-2147483648。
2、首先jdk中定义int占4个字节32位，32位就是jvm仅仅给分配32个格子的空间，用以存放数据。
3、计算机中用0和1存放数据。那么，32个格子中放满0或1的方法，有2的32次方种。
4、但是java中int有正负之分，所以32个格子中占用一个格子标识正负，仅仅能用31个格子来标识数值。最后int能标识的最大/最小数字是：2的31次方即+/- 2147483648。取值范围即为二者之间。
```

##### 集合

![img](assets/20160706172512559.jfif)

List 和 Set 是存储单列数据的集合，Map 是存储键和值这样的双列数据的集合；List 中存储的数据是有顺序，并
且允许重复；Map 中存储的数据是没有顺序的，其键是不能重复的，它的值是可以有重复的，Set 中存储的数据是无序的，且不允许有重复，但元素在集合中的位置由元素的 hashcode 决定，位置是固定的（Set 集合根据 hashcode 来进行数据的存储，所以位置是固定的，但是位置不是用户可以控制的，所以对于用户来说 set 中的元素还是无序的）

List接口下实现类：

```
LinkedList：基于链表实现，链表增删快，查找慢
ArrayList：：基于数组实现，非线程安全的，效率高，便于索引，但不便于插入删除
Vector：基于数组实现，线程安全的，效率低

ArrayList 底层结构是数组,底层查询快,增删慢。
LinkedList 底层结构是链表型的,增删快,查询慢。
voctor 底层结构是数组 线程安全的,增删慢,查询慢。
```

Map：

```
HashMap：基于 hash 表的 Map 接口实现，非线程安全，高效，支持 null键值；
HashTable：线程安全，低效，不支持 null 值和 null 键；
LinkedHashMap：是 HashMap 的一个子类，保存了记录的插入顺序
ConcurrentHashMap：HashTable的替代品，ConcurrentHashMap与HashTable都可以用于多线程的环境，但是当Hashtable的大小增加到一定的时候，性能会急剧下降，因为迭代时需要被锁定很长的时间。因为ConcurrentHashMap引入了分割(segmentation)，不论它变得多么大，仅仅需要锁定map的某个部分，而其它的线程不需要等到迭代完成才能访问map。简而言之，在迭代的过程中，ConcurrentHashMap仅仅锁定map的某个部分，而Hashtable则会锁定整个map。
```

Set 接口：

```
HashSet：底层是由HashMap实现，不允许集合中有重复的值，使用该方式时需要重写 equals()和 hashCode()方法
LinkedHashSet：继承与 HashSet，同时又基于 LinkedHashMap 来进行实现，底层使用的是 LinkedHashMap）
```

##### List a=new ArrayList()和 ArrayList a =new ArrayList()的区别

```
List list = new ArrayList();这句创建了一个ArrayList的对象后把上溯到了List。此时它是一个 List 对象了，有些ArrayList 有但是 List 没有的属性和方法，它就不能再用了。而 ArrayList list=new ArrayList();创建一对象则保留了ArrayList 的所有属性。 所以需要用到 ArrayList 独有的方法的时候不能用前者
```

##### Java 中 ArrayList 和 Linkedlist 区别



##### 多系统服务器交互

1、两个项目同时访问一个数据库的中间库，触发器分发数据库到项目数据库中

2、使用webservice接口实现

##### Oracle中存储过程

优点：存储过程只在创造时进行编译，以后每次执行存储过程都不需再重新编译，而一般[SQL语句](https://www.baidu.com/s?wd=SQL%E8%AF%AD%E5%8F%A5&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)每执行一次就编译一次,所以使用存储过程可提高数据库执行速度。
当对数据库进行复杂操作时(如对多个表进行Update、Insert、Query、Delete时），可将此复杂操作用存储过程封装起来与数据库提供的事务处理结合一起使用。
3.存储过程可以重复使用,可减少数据库开发人员的工作量。
4.安全性高,可设定只有某用户才具有对指定存储过程的使用权。

##### 类与接口区别

```
1、接口类似于类，但接口的成员都没有执行方式，它只是方法、属性、事件和索引的组合而已，并且也只能包含这四种成员；类除了这四种成员之外还可以有别的成员(如字段)。
2、不能实例化一个接口，接口只包括成员的签名；而类可以实例化(abstract类除外)。
3、接口没有构造函数，类有构造函数。
4、接口不能进行运算符的重载，类可以进行运算符重载。
5、接口的成员没有任何修饰符，其成员总是公共的，而类的成员则可以有修饰符(如：虚拟或者静态)。
6、派生于接口的类必须实现接口中所有成员的执行方式，而从类派生则不然。
```

##### 获取日期时间

```java
Calendar cal = Calendar.getInstance(); //获取日历实例
System.out.println(cal.get(Calendar.YEAR));
System.out.println(cal.get(Calendar.MONTH)); // 0 - 11
System.out.println(cal.getTime()); //获取当前时间 格式化

// Java 8
LocalDateTime dt = LocalDateTime.now();  //通过LDT now()方法获取当前时间实例
System.out.println(dt.getYear()); 
System.out.println(dt.getMonthValue()); // 1 - 12
System.out.println(dt.getDayOfMonth());
System.out.println(dt.getHour());

System.out.println(Clock.systemDefaultZone().millis()); //当前时间戳
System.out.println(Clock.systemDefaultZone().getZone()); //获取时区
```

##### 如何将一个 java 对象序列化到文件里

```java
1. //对象输出流
2. ObjectOutputStream objectOutputStream = 
3. new ObjectOutputStream(new FileOutputStream(new File("D://obj")));
4. objectOutputStream.writeObject(new User("zhangsan", 100));
5. objectOutputStream.close();
6. //对象输入流
7. ObjectInputStream objectInputStream = 
8. new ObjectInputStream(new FileInputStream(new File("D://obj")));
9. User user = (User)objectInputStream.readObject();
10. System.out.println(user);
11. objectInputStream.close();
```

##### java导出excel图表等

[POI开源组件](http://http//poi.apache.org/download.html)实现将数据导出到Excel文件中

##### 如果 cookie 被禁用了怎么办

保持登录的关键不是 cookie，而是通过cookie 保存和传输的 session ID，其本质是能获取用户信息的数据。除了 cookie，还通常使用 HTTP 请求头来传输。但是这个请求头浏览器不会像 cookie 一样自动携带，需要手工处理

##### 设计模式

```
创建型模式，共五种：工厂方法模式、抽象工厂模式、单例模式、建造者模式、原型模式。
结构型模式，共七种：适配器模式、装饰器模式、代理模式、外观模式、桥接模式、组合模式、享元模式。
行为型模式，共十一种：策略模式、模板方法模式、观察者模式、迭代子模式、责任链模式、命令模式、备忘录模
式、状态模式、访问者模式、中介者模式、解释器模式
```

##### 单例设计模式

```
饿汉式：
// 直接创建对象
// 私有化构造函数
// 返回对象实例

懒汉式：
// 声明变量
// 私有构造函数
// 提供对外方法
```

##### 工厂方法模式

```
工厂方法模式分为三种：普通工厂模式，就是建立一个工厂类，对实现了同一接口的一些类进行实例的创建。
多个工厂方法模式，是对普通工厂方法模式的改进，在普通工厂方法模式中，如果传递的字符串出错，则不能
正确创建对象，而多个工厂方法模式是提供多个工厂方法，分别创建对象。
静态工厂方法模式，将上面的多个工厂方法模式里的方法置为静态的，不需要创建实例，直接调用即可
```

