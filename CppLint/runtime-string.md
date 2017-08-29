Pattern: Static/global string declaration

Issue: -

## Description

Checks for static/global STL string declarations at the top level. This is dangerous because the C++ language does not guarantee that globals with constructors are initialized before the first access, and also because globals can be destroyed when some threads are still running.

## Further Reading

* [Google C++ Style Guide - Static and Global Variables](https://google.github.io/styleguide/cppguide.html#Static_and_Global_Variables)