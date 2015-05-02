---
layout: post
title: "Syntaxterror: C++"
modified: 2015-05-01
tags: ["C++","Syntaxterror","Programming"]
share: true
comments: true
description: "All you need to know when you learn C++ and even Google doesn't help you out."
---
## Backstory

You may want to [skip](#weird-syntax) this part, as it is only a tiny backstory, of why I write this article.

Before I digged into C++ programming I tried to teach it myself from the very basics by learning C-syntax first. So I bought [_"C from A to Z"_](http://openbook.rheinwerk-verlag.de/c_von_a_bis_z/) and read it in a couple of days.  
Unfortunately this book gave me almost nothing valuable. Either I already knew the basic stuff like loops and such, or it kind of failed to teach me the things I didn't know of, in my case it was the pointer-drama.  
(Back in the days I always asked myself why I have to use the `*`-operator to declare a variable and then use the same operator to dereference it again to refer to the actual object.)

After that, I decided to learn C++ entirely from free online sources. So I downloaded alot of open source libraries, such as [Ogre3D](), the [DOOM]()-engine and other stuff. I also had a look into the standard library implementations. While scrolling throught those files, I encountered for me unknown syntax parts, which I needed to know what they actually do.

But how does one google for syntax?

Therefore I decided to write up this collection of C++ syntax, that is kind of hard to search for.

## What is this weird syntax? {#weird-syntax}

Note: the following sections do not have a specific order.

### Declaration vs. Definition

The following is an excerpt from [stackoverflow.com](http://stackoverflow.com/a/1410632/3087952):

Declaration:
: A declaration introduces an identifier and describes its type, be it a type, object, or function. A declaration is **what the compiler needs** to accept references to that identifier. These are declarations:

  ~~~
extern int number;              // a global variable
int fooBar( int a , int b );    // a prototype
class Baz;                      // a forward declaration
~~~

Definition:
: A definition actually instantiates/implements this identifier. It's **what the linker needs** in order to link references to those entities. These are definitions corresponding to the above declarations:

  ~~~
int number = 42;

int fooBar( int a , int b )
{
    return a + b;
}

class Baz
{
    public:
        int member;
};
~~~



