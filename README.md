# rsa.principle

#### 介绍

RSA加密原理联系（采用aardio编写），参考pygmp2库的用法，手动封装gmp库（libgmp）实现大数运算。
后续会不定期更新，作为CTF RSA的解题工具

#### 下载

参考release文件，也可下载aardio手动编译

#### 封装的一些小疑问

封装gmp库参考的是math.bignum，其中aardio利用元表进行运算符重载

```java
class bignum{
	ctor(num){
		this.bigNumber = ..raw.buffer(_buffSize);
		this@ = _meta;
	};
}
```

接着定义元属性

```java
_meta = {
		_get = {
			add = function(n){
				var c = ..math.bignum();
				_dll.bignum_add(owner,..math.bignum(n),c)
				return c;
			};
...
}
```

实现重载方法

```java
_add = function(b) {
    return owner.add(b);
};
```

其中位于_meta._get.add，若在利用对象使用owner（复制构造函数），则垃圾回收会崩溃


#### 软件截图

![image](https://github.com/sfantree/rsa.principle/blob/master/img/1.jpg)

