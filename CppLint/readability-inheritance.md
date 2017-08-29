Pattern: Redundant `override`/`virtual` annotation

Issue: -

## Description

For clarity, use exactly one of `override`, `final`, or `virtual` when declaring an override. Rationale: A function or destructor marked `override` or `final` that is not an override of a base class virtual function will not compile, and this helps catch common errors. 

The specifiers serve as documentation; if no specifier is present, the reader has to check all ancestors of the class in question to determine if the function or destructor is virtual or not.


## Further Reading

* [Google C++ Style Guide - Inheritance](https://google.github.io/styleguide/cppguide.html#Inheritance)	