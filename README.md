#总结js函数中的arguments对象

1.arguments对象不能显式创建，arguments对象只有函数开始时才可用，而且arguments是js中的保留字。不要占用这个名字

2.函数的 arguments 对象并不是一个数组

```
function test(a,b){
  console.log(arguments instanceof Array);   
}

test("hahh","hehe") //false

```

3.访问单个参数的方式与访问数组元素的方式相同。索引 n 实际上是 arguments 对象的 0…n 属性的其中一个参数。

```
function test(a,b){
  console.log(arguments[0]);
}

test("hahh","hehe")   // "hahh"

```

3.通过 arguments 属性(相对于Function来说)，函数可以处理可变数量的参数。arguments 对象的 length 属性包含了传递给函数的参数的数目。对于arguments 对象所包含的单个参数，其访问方法与数组中所包含的参数的访问方法相同。

```
function test(a,b){
  console.log(arguments.length);
}

test("hahh","hehe")   // 2

```

4.说明一下arguments与真正传的形式参数是一致的：比如，你给函数传了一个叫param的参数，并且只有这一个参数，那么param与arguments[0]都是对这个参数值的引用

```
function test(a,b){
  arguments[0] = "我改变了";
  console.log(a);
}

test("hahh","hehe")   // "我改变了"

```
