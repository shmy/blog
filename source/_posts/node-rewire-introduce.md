---
title: js使用rewire对私有变量/函数进行测试
date: 2020-04-21 13:26:32
tags: ["node", "backend"]
---

## 什么是rewire

> [`rewire`](https://github.com/jhnns/rewire)，它的基本功能与`require`相同，都是用于导入模块，只是，它会为导入的模块添加两个特殊的函数：**`__get__`**与**`__set__`**。顾名思义，这两个函数可以分别用于获取和修改模块中的变量/函数。测试的时候，当我们需要获取或者重写私有变量/函数，`rewir`e非常有用。

<!-- more -->



## 简单实用

> example.service.js

```js
const getUserInfo = (userId) => {
  
  const user = UserProfile.findOne({id: userId});
  const email = getUserOrder(user.company);
  return {...user, email};
};

const getUserEmail = (userCompany) => {

  if (!userCompany) {
    return "";
  }
  return "some@some.com";
};

exports.getUserInfo = getUserInfo;
```

> 以上代码我们在测试时，无法直接获取到`getUserEmail` 方法进行测试，也不会在统计到覆盖率中，因为这个函数没有被其他函数直接或间接调用；
>
> 在我们工作中，常常有许多这种私有函数或者变量，只在当前模块内定义和使用并没有导出；如果我们有直接或间接调用这个函数，并且这个私有函数有很多分支条件的话，跑完测试后，不一定能到覆盖到全部的分支；
>
> 所以，`rewire`模块可以提供一些`api`帮我们直接拿到或者设置这个私有函数/变量，这样的话，我们就能够很方便的对其中各种分支条件等等测试。

> example.service.test.js

```js
const rewire = require("rewire");
const exampleService = rewire("./example.service");
const getUserEmail = exampleService.__get__("getUserEmail");

expect(getUserEmail()).toEqual("");	// 👌
expect(getUserEmail(1)).toEqual("some@some.com"); // 👌
```

> 在实践中，为了简化测试和节省时间，我们通常需要去重写函数调用的外部函数，这时可以选择使用`rewire`模块实现。

## babel插件

> 此外：[babel-plugin-rewire](https://github.com/speedskater/babel-plugin-rewire) 提供了`babel`的插件，方便和`jest`等测试框架集成。