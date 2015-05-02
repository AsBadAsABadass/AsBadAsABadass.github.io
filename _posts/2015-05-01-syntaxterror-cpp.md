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
{:.no_toc}

You may want to [skip](#weird-syntax) this part, as it is only a tiny backstory, of why I write this article.

Before I digged into C++ programming I tried to teach it myself from the very basics by learning C-syntax first. So I bought [_"C from A to Z"_](http://openbook.rheinwerk-verlag.de/c_von_a_bis_z/) and read it in a couple of days.  
Unfortunately this book gave me almost nothing valuable. Either I already knew the basic stuff like loops and such, or it kind of failed to teach me the things I didn't know of, in my case it was the pointer-drama.  
(Back in the days I always asked myself why I have to use the `*`-operator to declare a variable and then use the same operator to dereference it again to refer to the actual object.)

After that, I decided to learn C++ entirely from free online sources. So I downloaded alot of open source libraries, such as [Ogre3D](), the [DOOM]()-engine and other stuff. I also had a look into the standard library implementations. While scrolling throught those files, I encountered for me unknown syntax parts, which I needed to know what they actually do.

But how does one google for syntax?

Therefore I decided to write up this collection of C++ syntax, that is kind of hard to search for and provide you some terms, names and maybe links.

## What is this weird syntax? {#weird-syntax}
{:.no_toc}

- TOC
{:toc}

Note: the following sections do not have a specific order.

### Declaration vs. Definition

The following is an excerpt from [stackoverflow.com](http://stackoverflow.com/a/1410632/3087952):

Declaration:
: A declaration introduces an identifier and describes its type, be it a type, object, or function. A declaration is **what the compiler needs** to accept references to that identifier. These are declarations:

  ~~~ cpp
  extern int number;              // a global variable
  int fooBar( int a , int b );    // a prototype
  class Baz;                      // a forward declaration
  ~~~

Definition:
: A definition actually instantiates/implements this identifier. It's **what the linker needs** in order to link references to those entities. These are definitions corresponding to the above declarations:

  ~~~ cpp
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

### What is that colon `:` for? {#colon}

This colon is valid in two places:

- after constructors as _initializer list_
- after a class definition for inheritance

~~~ cpp
class Foo
{
    public:
        int member;
        
        Foo( int value ) : member( value ) // initializer list
        {
        }
};

class Bar : Foo // Bar inherits (private'ly) from Foo
{
};
~~~

{% highlight cpp %}
class Foo
{
    public:
        int member;
        
        Foo( int value ) : member( value ) // initializer list
        {
        }
};

class Bar : Foo // Bar inherits (private'ly) from Foo
{
};
{% endhighlight %}

**Note:** The colon also appears in labels and the ternary `?:`-operator, but these aren't exclusive to C++, so I left them out.

### What is this tilde `~` for? {#tilde}

The tilde befor a method marks the *destructor*:

~~~ cpp
class Foo
{
    public:
        Foo();     // constructor
        ~Foo();    // destructor
};
~~~

### Variadic Templates vs. Vairable templates

**Varia*dic* templates** are templates with an arbitrary number of arguments.

See here for more:

- [TODO]()

**Varia*ble* templates** are variables that can be templated.

Example:

~~~ cpp
template< typename T >
constexpr T Pi = T( M_PI );

auto pi = Pi< float >;
~~~

See here for more:

- [TODO]()

### What does `= 0` mean?

Such methods are *pure virtual* methods. Any class, that inherits such a class **must** override this method. A pure method needs to be `virtual`.

~~~ cpp
class Foo
{
    virtual void method() = 0; // pure virtual function
};

class Bar : Foo
{
    int method(); // error: must override void method();
};

class Baz : Foo
{
    void method();                       // OK
    virtual void method()                // better
    virtual void method() = override;    // best
};
~~~























