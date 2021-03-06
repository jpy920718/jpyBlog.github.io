---
title: Typescript 泛型 类型变量 T
date: 2019-01-07 09:49:40
tags: 
    - Typescript
---

类型变量：确保输出的返回值与传入的形参的类型一致，它是一种特殊的变量，表示类型不表示值。
```javascript
    function func<T>(arg: T): T{
        return arg;
    }
```
通过给函数添加了类型变量 T 。T 可以捕获用户传入的类型，使用 T 作为返回值的类型。这样就可以知道发返回值的类型和参数类型是一致的。

把可以适用于多种类型的函数称为泛型函数。

我们可以使用两种方式来使用泛型函数
* 第一种：明确指定 T 为string类型, 并传递一个string参数给函数
```javascript
    func<string>('123')
```

* 第二种：利用类型推论，编译器根据传入的参数自动确定 T 的类型
```javascript
    func(123);
    func('123');
```
不一定使用尖括号明确指定传入参数的类型，编译器可以自己判断传入参数的类型，然后将 T 设置为传入参数的类型。
如果编译器不能自动的推断出类型的话，只能明确传入 T 的类型。
<!--more-->