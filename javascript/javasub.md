### 构造函数的缺点

自定义对象时，以构造函数为模板，对象的属性和方法，可以定义在构造函数内部。每当获取对象时都会在内存中创建新的对象属性和方法，这既是增加页面代码量有浪费内存（系统资源）。

同一个构造函数的对象实例之间无法共享属性，而所有的方法都是同样的行为，因此属性和方法完全应该共享。但无法共享这就是缺点。

### prototype属性

JavaScript中每一个对象都继承另一个对象，父类对象称之为“原型”（prototype）对象。**只有null除外，其他都有自己的原型对象**

原型对象的作用就是定义所有数理化对象共享的属性和方法。这也是他被称为原型对象的原因，而实例化对象可以视作从原型对象衍生出来的子对象。

由于JavaScript的所有对象都是构造函数（只有null除外）。而所有构造函数都有prototype属性（其实是所有函数都有prototype属性），所以所有对象都有自己的原型对象。

### 原型链

对象的属性和方法，有可能是定义在自身内，也有可能是定义在它的原型对象上。由于原型对象本身也是对象，又有自己的原型，所有生成了一条原型链（prototype chain）。例如，a对象是b对象的原型，b对象是c对象的原型，依次类推。

如果那么一层层地上溯，所有对象的原型最终都可以上溯到Object对象上。Object对象也有原型就是一个没有任何属性和方法的null对象，而null对象没有自己的原型。

```
function Student(Name){
    this.name=Name;
}
var stu1=new Student('aklman');
console.log(Student.prototype);
console.log(Student.prototype.constructor.prototype);
//由于对象自身直接获取原型对象，最终的大对象就是object,也就是说，在JavaScript中所有对象（不管从何而来）都基于object大对象，而最大对象Object的原型指向null，也就是没有
console.log(stu1.__pro__.__proto__.__proto__);
```

原型链的作用是读取对象某个属性时，JavaScript引擎先寻找对象本身的属性，如果找不到就找它的原型（父类对象），如果还是找不到就找原型的原型。如果直到最顶层的Object。prototype还是找不到，则返回undefined。

如果对象自身和它的原型，都定义了一个同名属性，那么优先读取对象自身的属性，这叫**覆盖\(overriding\)**。

### 原型操作

##### 1. constructor属性

对象有一个constructor属性指向原型对象所在的构造函数

```
function Student(name){
    this.name=name;
}
var stu=new Student('aklman');
console.log(stu.constructor);
```

##### 2. 设置获取原型对象

Object.getPrototypeOf\(\)方法返回一个对象的原型对象，也就是通过它获取原型对象，这是标准的方法。

```
function Student(name,Class){
    this.name=name;
}
var stu=new Student('aklman');
//获取stu对象的原型对象
var s=Object.getPrototypeOf(stu);
console.log(s);
```

Object.setPrototypeOd\(\)为现有对象设置原型对象，第一个参数是现有对象，第二个是要设置成为原型对象的对象，用这个方法来设置原型对象。

```
function Student(name,Class){
    this.name=name;
}
var ob={p:'aklan'};
var stu=new Student('Jappar');
//设置stu的原型对象ob
Object.setPrototypeOf(stu,ob); 
console.log(stu.p);//aklman
console.log(stu.name);//Jappar
console.log(Object.getPrototypeOf(stu));//由大对象提供的getPrototypeOf方法获取对象的原型对象
```

##### 3. 获取原型对象方法及比较

获取原型对象的方法有三种：

```
obj.__proto__
obj.constructor.prototype
Object.getPrototypeOf(obj)
```

其中前两个方法不是很友好，最新的ES6标准规定，proto属性只有浏览器才需要部署，其他环境可以不部署。而obj.constructor.prototype在手动改变原型对象时，会失效。

```
function Student(name,Class){
    this.name=name;
}
var ob={p:'aklman'};
var stu=new Student('Jappar');
//使用constructor属性获取原型对象
console.log(stu.constructor.prtototype);

//修改stu的原型对象为ob
Object.setPrototypeOf(stu,ob);

//使用getPrototypeOf方法来查看stu的原型对象为ob
console.log(Object.getPrototypeOf(stu));

//使用constructor属性获取原型对象为Object，这是错误的,构造函数无法修改对象的原型对象
console.log(stu.constructor.prototype);
```

最好使用Object.getPrototypeOf\(\)方法获取原型对象

```
function Student(name){
    this.name=name;
}
vat stu=new Student('aklman');
//1.构造函数获取原型对象
console.log(stu.constructor.prototype);
//2.由对象自身获取原型对象
console.log(stu.__proto__);
//3.有大树提供的getPrototypeOf()方法获取对象的原型对象
console.log(Obj.getPrototypeOf(stu));
```



