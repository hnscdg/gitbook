　C\#在操作类型转换时，提供了 as 和 is ， 显式，隐式类型转换，由于显式和隐式类型转换比较容易理解，这里主要介绍下 is 和 as 的转换。

### **is  转换**

is 操作符指定一个对象类型是否兼容于所指定的类型，返回的是 Bollen 值，true 或false, is 操作符永远不会抛出异常。

如果引用的对象是null, is 操作符总是返回false,因为没有可检查其类型的对象。

```
Object o= new Object();
 
Boolean b1= (o is object);
 
Boolean b2=(o is Employee);


if(o is Employee){
 
 Employee e= (Employee)o;
}
```

　　在这段if 代码中，CLR 实际上会检查两次对象的类型，is 操作符首先核实o是否兼容于Employee类型，如果是，那么if语句内部执行转换时，CLR 会再次核实o是否兼容于 Employee 类型，CLR 的类型检查增强的安全性，但无疑也会对性能造成一定影响，这是因为，CLR 必须首先判断变量o引用的对象的实际类型，然后CLR 必须遍历继承层次结构，用每个基类型去核对指定的类型（Employee）,由于这是一种相当常用的编程模式，所以C\#专门提供了as 操作符，目的就是简化这种代码的写法，同时提升性能。

### **as 转换符**

as 操作符的工作方式与强制类型转换一样 ，只是它永远不会抛出一个异常，如果对象不能转换，结果就是null,强制转换则会抛出异常

。以下为示例：

```
Employee e = o as Employee;
 
if(e !=null){
 
 //要实现的业务逻辑
 
}
```

 在这段代码中， CLR 核实o 是否兼容于Employee, 如果是，as 会返回对同一对象的一个非null 引用 ，如果o 不兼容于Employee 类型，as 操作符会返回null,值 得注意的是 as 操作符造成CLR 只校验一次对象的类型，if语句只是检查e是否为null, 这样的检查速度比校验对象的类型快的多。

