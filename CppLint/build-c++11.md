Pattern: Unapproved C++11 element

Issue: -

## Description

Use libraries and language extensions from C++11 when appropriate. Consider portability to other environments before using C++11 features in your project. The following C++11 features may not be used:

  - Compile-time rational numbers (`<ratio>`), because of concerns that it's tied to a more template-heavy interface style.
  - The `<cfenv>` and `<fenv.h>` headers, because many compilers do not support those features reliably.
  - Ref-qualifiers on member functions, such as `void X::Foo() &` or `void X::Foo() &&`, because of concerns that they're an overly obscure feature.
  
  
As with Boost, some C++11 extensions encourage coding practices that hamper readability — for example by removing checked redundancy (such as type names) that may be helpful to readers, or by encouraging template metaprogramming. Other extensions duplicate functionality available through existing mechanisms, which may lead to confusion and conversion costs.

  
## Further Reading

* [Google C++ Style Guide - C++11](https://google.github.io/styleguide/cppguide.html#C++11)
