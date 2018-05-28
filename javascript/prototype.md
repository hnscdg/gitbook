prototype

![](/assets/prototype.jpg)

Description:

#### 构造函数Foo\(\)

构造函数的原型属性Foo.prototype指向了原型对象，在原型对象里有共有的方法，所有构造函数声明的实例（这里是f1，f2）都可以共享这个方法。

#### 原型对象Foo.prototype

Foo.prototype保存着实例共享的方法，有一个指针constructor指回构造函数

#### 实例

f1和f2是Foo这个对象的两个实例，这两个对象也有属性\_\_proto\_\_，指向构造函数的原型对象，这样子就可以像上面1所说的访问原型对象的所有方法啦。

  
构造函数Foo\(\)除了是方法，也是对象啊，它也有\_\_proto\_\_属性，指向谁呢？  
指向它的构造函数的原型对象呗。函数的构造函数不就是Function嘛，因此这里的\_\_proto\_\_指向了Function.prototype。  
其实除了Foo\(\)，Function\(\), Object\(\)也是一样的道理。

原型对象也是对象啊，它的\_\_proto\_\_属性，又指向谁呢？  
同理，指向它的构造函数的原型对象呗。这里是Object.prototype.

最后，Object.prototype的\_\_proto\_\_属性指向null。

