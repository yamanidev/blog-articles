---
external: false
title: 'Difference Between var and let in JavaScript'
description: ''
date: 2021-03-19
---

One of the features that ES6 (ECMAScript 2015) introduced was **let** and **const** which raised some confusion between **var** and **let**. If we could already declare variables with **var** why do we need **let**? What's the difference between them? Today we will discover that!

## The legendary battle: let vs var

### 1) Scope

Variables declared with **var** are said to be function scoped. They are only known inside the body of the function where they were declared:

```javascript
function test() {
  var something = 'Banana man';
  console.log(something);
}

test(); // "Banana man"
console.log(something); // ReferenceError
// Because we are outside of the variable's scope
```

Another example would be:

```javascript
for (var i = 0; i < 3; ++i) {
  //some sick code
}
console.log(i); // 3
```

Variables declared with **let** are said to be block scoped. They are only known inside of the block they were declared in:

```javascript
for (let i = 0; i < 3; ++i) {
  //another sick code
}
console.log(i); // ReferenceError
```

A block is code between the curly brackets {}

### 2) Hoisting

But what if...

```javascript
console.log(something); // undefined
var something = 'Banana boy';
```

We wouldn't expect such result because it doesn't make sense, how the hell would it recognize the variable **something** if it was not declared yet?

The answer to this is **hoisting**.

Hoisting in Javascript is a dense topic that I will write about in separate article, for now, I will briefly summarize it.

Hoisting is a Javascript engine behavior that recognizes variables and functions before they're initialized.

You can **picture** it as moving all the declarations to the top of the code, but that's not what happens, your code does not move, it is just a way for you to understand it more easily!

In the example above, we notice that the variable **something** was initialized with the value **undefined** before reaching the initialization (with the value "Banana boy"), that's exactly what hoisting does.

It is "equivalent" to:

```javascript
var something; // declaration "moved" to the top
console.log(something); // undefined
something = 'Banana boy';
```

Now when it comes to variables declared with **let** we do not encounter such result:

```javascript
console.log(something); // ReferenceError
let something = 'banana';
```

We cannot access or use variables declared with **let** before initialization.

Does that mean that they are not hoisted?

No. They are indeed hoisted, in a different way. I will explain how that is the case in detail in a separate article to keep it simple.

**All in all**

- Variables defined with **var** are always known inside of the function they are defined in, before the declaration (with **undefined**) and after it (with the value you assigned).

- Variables defined with **let** are known inside of the block they are defined in, only AFTER the declaration.

### 3) Global object property

When a variable is defined globally with **var**, it becomes a property of the window object:

```javascript
var x = 'Banana girl';
console.log(window.x); // "Banana girl"
```

That is not the case with global variables defined with **let** though:

```javascript
let y = 'boi';
console.log(window.y); // undefined
```

### 4) Redefining

You can redefine the same variable with **var**.

But when you try to do that with **let**, it raises SyntaxError:

```javascript
var x = 30;
var x = 300; // Valid
let boo = 'cacao';
let boo = 'never mind'; // Uncaught SyntaxError
```

### Why was "let" introduced?

- Declaring variables with **var** is prone to error. When we use a variable, it is desirable for it to "stick around" only when needed (in other words, the block it was declared in). That's why **let** declares block-scoped variables. Our code becomes less prone to error.

- Attaching variables to the **window** object (by declaring them globally with **var**) is problematic. When working with different modules, it is possible to run into conflicts (different variables with the same name, resulting in one overriding the other).

- There is no reason for being able to redeclare variables, it makes code more confusing and is not a sensible decision. **let** does not let you do that (pun semi intended).

## Thank you for reading!

That was the main difference between **var** and **let**, I hope you learned a thing or two!

Any feedback or constructive critique is warmly welcomed and appreciated, so please tell me what you think in the comments so I can better the quality. Thanks for reading ❤️!

Follow my blog and my [Twitter](https://twitter.com/yamanidev) for more!

Have a nice one!
