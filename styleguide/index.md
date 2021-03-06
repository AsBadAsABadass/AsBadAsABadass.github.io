---
layout: page
title: Styleguide
description: "My personal guide on coding style."
modified: 2015-4-28
tags: [programming]
share: false
comments: false
---

### Naming Convention

**`camelCase`**
: start lowercase, no underscores, each seperate word starts uppercase, abbreviations either uppercase in total or just the first character

**_`PascalCase`_**
: same as _camelCase_, but starts always with a capital letter

**_snake_case_**
: all lowercase (also abbreviations), words seperated by underscores

**_ALL_CAPS_**
: like _snake_case_, but only uppercase

#### Local Variable Names

Local variable names, which are dropped at the end of a scope should be named in _camelCase_.  
(optionally I currently experiment with _snake_case_ for local variables)

~~~
{
    int fooBar;
    int foo_bar;
}
~~~

#### (statefull) Class Names & Methods

Class names, that contain logic should be in _PascalCase_.
Methods should be in _camelCase_.

~~~
class FooBar
{
    void methodBar();
};
~~~

#### (stateless) Struct/Union Names and simple C-Style type aliases

~~~
typedef float3 float[3];

struct aabb
{
    float3 center;
    float3 extent;
};
~~~


