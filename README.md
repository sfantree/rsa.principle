# rsa.principle

#### 介绍
RSA加密原理演示（aardio编写），封装gmp库实现大数运算

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


#### 软件架构
软件架构说明


#### 安装教程

1.  xxxx
2.  xxxx
3.  xxxx

#### 使用说明

1.  xxxx
2.  xxxx
3.  xxxx

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
