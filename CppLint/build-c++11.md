Pattern: Unapproved C++11 element

Issue: -

## Description

Use libraries and language extensions from C++11 when appropriate. Consider portability to other environments before using C++11 features in your project. 

### Definition

C++11 contains [significant changes](https://en.wikipedia.org/wiki/C%2B%2B11) both to the language and libraries. 

### Pros

C++11 was the official standard until august 2014, and is supported by most C++ compilers. It standardizes some common C++ extensions that we use already, allows shorthands for some operations, and has some performance and safety improvements.

### Cons

The C++11 standard is substantially more complex than its predecessor (1,300 pages versus 800 pages), and is unfamiliar to many developers. The long-term effects of some features on code readability and maintenance are unknown. We cannot predict when its various features will be implemented uniformly by tools that may be of interest, particularly in the case of projects that are forced to use older versions of tools.

As with Boost, some C++11 extensions encourage coding practices that hamper readability—for example by removing checked redundancy (such as type names) that may be helpful to readers, or by encouraging template metaprogramming. Other extensions duplicate functionality available through existing mechanisms, which may lead to confusion and conversion costs.

### Decision

C++11 features may be used unless specified otherwise. In addition to what's described in the rest of the style guide, the following C++11 features may not be used:

  - Compile-time rational numbers (`<ratio>`), because of concerns that it's tied to a more template-heavy interface style.
  - The `<cfenv>` and `<fenv.h>` headers, because many compilers do not support those features reliably.
  - Ref-qualifiers on member functions, such as `void X::Foo() &` or `void X::Foo() &&`, because of concerns that they're an overly obscure feature.
  
## Further Reading

* [Google C++ Style Guide - C++11](https://google.github.io/styleguide/cppguide.html#C++11)
