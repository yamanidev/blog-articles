---
external: false
title: 'Underscores and Naming Conventions in Python'
description: ''
date: 2021-03-21
---

## Introduction

Software engineers are known for having heated debates with each other on the different tools and technologies and their preferences. Yet they all agree on one specific thing, and that is **consistency of code is vital**.

Lack of the latter causes unpleasant troubles within teams (and even with one’s self) that makes everyone’s days a living hell.

**Picture this**: person A names their variables with _styleA_, person B with _styleB_ and so on and so fourth.

Can you imagine how the code base would look like? It would be a wild jungle, making readability and maintainability pure fantasy!

For this purpose, naming conventions and styles were founded for a universal code that is standards compliant and therefore, less error-prone.

## What is PEP8?

PEP8 is a style guideline that provides conventions for Python code which helps us with writing clean code.

This style guide is kept up-to-date as the language evolves, adding conventions and removing other ones that became obsolete. So you should always be tuned in.

This is the official [PEP8 Documentation](https://www.python.org/dev/peps/pep-0008/) and I highly recommend you take a look at it from time to time.

## General conventions in Python

- Variables names should not be a single letter uppercase **i**, a lowercase **L** or an uppercase **O**.

- Variable names should not start with numbers or an uppercase letter.

- All variable names should be in lowercase.

- Long variable names should be separated with an underscore. This style is called **snake-case**, the style used in Python.

**Class name examples**: Fruit, Vegetable, CoolBeans…

- All function names (except factory functions) should be in lowercase.

**Note**: factory functions are functions that return objects, thus behaving like class declarations.

- Class and factory function names follow the PascalCase naming convention (first letter of every word is capitalized).

```python
this_is_how_you_name_me = "comply now or perish"
style_name = "snake-case"
```

### Constants

In Python, there is no such thing as a constant, everything that you declare can be modified and overwritten afterwards. We use variables that we don’t modify instead (smart I know).

So how do we distinguish between variables and “constants”?

We write constant names in **snake-case** and in capital letters:

```python
YOU_BETTER_NOT_TOUCH_ME = "alright?"
PI = 3.14
```

And now getting to the underscores…

**Note**: underscores between words in a variable name do not hold any meaning!

## Underscores and access modifiers

Underscores in Python are discussed in the scope of **access modifiers**.

Access modifiers (private and protected) in reality do not exist in Python.

So how do we encapsulate our data? Let’s see:

### Protected access modifiers

Protected attributes/methods are prefixed with an underscore.

Protected members of a class can only be accessed either from within the class or from its sub-classes.

That is not the case with Python though; all protected members to Python are public.

Notice that:

```python
class Something:
   _banana = "I am hungry..."

print(Something._banana)
# "I am hungry..."
# The attribute should not
# have been displayed!
```

### Private access modifiers

Private attributes/methods are prefixed with a **dunder** (remember? They’re double underscores)

Private members of a class can only be accessed from within the class.

Now how the Python interpreter deals with this is very interesting!

```python
class SomethingElse:
    __me_is_back = "Am I private?"

x = SomethingElse()
print(x.__me_is_back)
# Raises error AttributeError
```

So what are you talking about? It clearly is private! We couldn’t access it from outside of the class!

Here is the fun part!

The Python interpreter performs name mangling in such a way that makes it seem as if the member is indeed private.

Let’s look at the namespace (attributes and methods) of the object **x** of class **SomethingElse** using the **dir()** method:

![Screenshot from 2021-03-21 19-52-15.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1616364854286/gUHT-n-pEm.png)

Look at the first element of the list!

So basically we can just:

```python
print(x._SomethingElse__me_is_back)
# "Am I private?"
```

We just accessed a private member from outside the class.

## Underscores and keywords

If you end up in a situation where you need to name your variables with a reserved keyword, the convention says that you should prefix the name with an underscore:

```python
def_ = "Ran out of creativity?"
```

Oh any by the way, if you wish to view all Python’s keywords:

```python
from keyword import kwlist
print(kwlist)
```

## Underscores and magic methods

Magic methods is a fancy name for special Python functions with a fixed name that are by convention enclosed with **dunders**.

We’ve seen in a previous example one of them being `__init__`

To state other magic methods, we have: `__add__` , `__str__` , `__and__`...

## Thank you for reading!

That was it! I hope you learned something new and enjoyed reading!
Any feedback or constructive critique is warmly welcomed and appreciated, so please tell me what you think in the comments so I can better the quality. Thanks for reading ❤️

Follow me on [Twitter](https://twitter.com/yamanidev) for more!

Have a nice one!

Photo by <a href="https://unsplash.com/@alvarordesign?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Alvaro Reyes</a> on <a href="/s/photos/programming?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
