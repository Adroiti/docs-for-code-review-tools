Pattern: Use of namespace using-directive

Issue: -

## Description

With few exceptions, place code in a namespace. Namespaces should have unique names based on the project name, and possibly its path. Do not use _using-directives_ (e.g. `using namespace foo`). Do not use inline namespaces.


## Further Reading

* [Google C++ Style Guide - Namespaces](https://google.github.io/styleguide/cppguide.html#Namespaces)