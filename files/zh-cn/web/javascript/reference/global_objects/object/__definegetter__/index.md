---
title: Object.prototype.__defineGetter__()
slug: Web/JavaScript/Reference/Global_Objects/Object/__defineGetter__
---

{{JSRef("Global_Objects", "Object")}} {{non-standard_header}} {{deprecated_header}}

## 概述

**`__defineGetter__`** 方法可以将一个函数绑定在当前对象的指定属性上，当那个属性的值被读取时，你所绑定的函数就会被调用。

## 语法

```plain
obj.__defineGetter__(prop, func)
```

### 参数

- `prop`
  - : 一个字符串，表示指定的属性名。
- `func`
  - : 一个函数，当 `prop` 属性的值被读取时自动被调用。

## 描述

`__defineGetter__` 方法可以为一个已经存在的对象设置（新建或修改）访问器属性，而 {{jsxref("Operators/get", "对象字面量中的 get 语法", "", 1)}} 只能在新建一个对象时使用。

## 示例

```js
// 请注意，该方法是非标准的：

var o = {};
o.__defineGetter__('gimmeFive', function() { return 5; });
console.log(o.gimmeFive); // 5


// 请尽可能使用下面的两种推荐方式来代替：

// 1. 在对象字面量中使用 get 语法
var o = { get gimmeFive() { return 5; } };
console.log(o.gimmeFive); // 5

// 2. 使用 Object.defineProperty 方法
var o = {};
Object.defineProperty(o, 'gimmeFive', {
  get: function() {
    return 5;
  }
});
console.log(o.gimmeFive); // 5
```

## 规范

不属于任何规范。

## 浏览器兼容性

{{Compat}}

## 相关链接

- [`Object.prototype.__defineSetter__()`](/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineSetter__)
- {{jsxref("Operators/get", "get")}} operator
- {{jsxref("Object.defineProperty()")}}
- [`Object.prototype.__lookupGetter__()`](/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/__lookupGetter__)
- [JS 指南：定义 Getter 和 Setter](/zh-CN/docs/Web/JavaScript/Guide/Working_with_objects#定义_getter_与_setter)
- [\[个人博文\] defineGetter\_\_ 和 \_\_defineSetter\_\_ 已被废弃](http://whereswalden.com/2010/04/16/more-spidermonkey-changes-ancient-esoteric-very-rarely-used-syntax-for-creating-getters-and-setters-is-being-removed/)
