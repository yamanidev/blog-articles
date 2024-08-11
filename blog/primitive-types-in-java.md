---
title: 'Primitive Types in Java'
description: 'I explain in this article what are primitives in Java with a mental model of memory as well as the different primitive types Java offers.'
canonicalUrl: "https://mohamedyamani.com/blog/primitive-types-in-java/"
pubDate: 2021-05-05
image: "/images/thumbnails/primitive-types-in-java.jpg"
imageAlt: "laptop monitor showing java class file on IDE"
---

## Introduction

You can think of data (variables) in our programs as boxes that contain values. They vary in **size** and in **shape**, but they’re fundamentally containers of data, nothing fancier.

We will be discussing the two types of data in Java through two separate articles; **primitives** and **object references**.

In this article, we’ll be discussing primitives.

## So what are primitives?

What I like to do personally before learning a new concept, is trying to guess its meaning through what the concept is called.

In this case, the concept is primitives. Let’s say I have no idea what that could mean in the Java context (or any other programming language, since this concept is shared across many of them).

What is a primitive in the English language? It could mean unsophisticated, old, simple etc.

These different meanings are all related to the concept we’re learning here!
Primitives are variables of fundamental types (they hold simple bit patterns), you can try to guess what data types existed in programming for the longest of time.

You can consider the previous guessing as a game you can play before you learn about the concept, that’s what I personally do and I have found that it helps!

Now enough of me rambling, there are 8 primitive types in Java (refer to this [link](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html) for more details):

- **boolean**: true or false values
- **char**: 16 bit-sized characters (it uses Unicode system and ASCII)
- **byte**: 8 bit-sized integers
- **short**: 16 bit-sized integers
- **int**: 32 bit-sized integers
- **long**: 64 bit-sized integers
- **float**: 32 bit-sized floating point numbers (numbers with a decimal point. eg: 3.14)
- **double**: 64 bit-sized floating point numbers

## So boxes you said?

Let’s expand a little on our previous box analogy which I very much like:

Every variable (whether it is of primitive type or an object) is a box with the following characteristics that differentiate it from the other ones:

- a **name**, which could be anything you could think of (except for ones that start with numbers, or [keywords](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html))
- a **type**, which describes the type of value the box can contain, a primitive or an object-type
- a **size**, which you do not need to worry yourself too much with, except for providing a value bigger than the box’s capacity.

## Important!

Let’s elaborate on the last characteristic which is the size of the box.

From the previous list of primitive types you can clearly notice that an **int **is bigger than a **short **and **byte**. And that a **long **is bigger than an **int**.

Consider this example:

```java
// Creating two boxes, x and y of types int and short respectively
int x = 30;
short y = x;
// This provokes an error (incompatible types)
```

Isn’t it strange though?

The value 30 can be contained by both boxes (the box of **int **of 32-bit and the box of **short **of 16-bit), so why is this happening?

What this `y = x` is doing, is that it is trying to copy the value of the box of `x` into the box `y`. Mind you that the box of `x` contains a value bigger than the capacity of the box `y`.

The value of 30 in **int **is not the same value in **short **due to the difference in size. And that’s why the compiler raises the error!

We cannot place a big box into a smaller one.

But how about going the other way around?

```java
short y = 30;
int x = y;
// Works like a charm
```

Always referring back to our box analogy, this worked because we are placing a small box (**short** variable) into a bigger box (**int** variable).

## How to differentiate between object-types and primitives?

We will get into objects and reference-type in the next article, but I’ll tell you how to differentiate between the two briefly:

Primitive variables only contain information, whereas objects (or reference-type variables) contain both information (also called state or attributes) and routines (properly called methods or behavior, which are functions in objects).

Primitives are NOT objects. So the next time someone rants about how everything in Java is an object, you know that’s not true.

You can access the members of an object (attributes and methods) using the “.” like so:

```java
object.someAttribute
object.someMethod()
```

As we said, we’ll get into all of this in the next article. I pointed this out to so that if you find the “.” used with a variable, know that it is an object and not a primitive!

## Thank you for reading!

That was it! I hope you learned something new and enjoyed reading!

Follow me on [Twitter](https://twitter.com/yamanidev) for more!

Have a nice one!

---
 
Thumbnail picture by [orbtal media](https://unsplash.com/@orbtalmedia?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/monitor-showing-computer-application-1td5Iq5IvNc?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
