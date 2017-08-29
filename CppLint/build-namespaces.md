Pattern: Malformed namespace

Issue: -

## Description

With few exceptions, place code in a namespace. Namespaces should have unique names based on the project name, and possibly its path. Do not use _using-directives_ (e.g. `using namespace foo`). Do not use inline namespaces.

When definitions in a .cc file do not need to be referenced outside that file, place them in an unnamed namespace or declare them static. Do not use either of these constructs in .h files.


## Further Reading

* [Google C++ Style Guide - Namespaces](https://google.github.io/styleguide/cppguide.html#Namespaces)
* [Google C++ Style Guide - Unnamed Namespaces and Static Variables](https://google.github.io/styleguide/cppguide.html#Unnamed_Namespaces_and_Static_Variables)
