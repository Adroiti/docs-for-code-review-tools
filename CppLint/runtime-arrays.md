Pattern: Use of variable-length array

Issue: -

## Description

Do not use nonstandard extensions. You may use portability wrappers that are implemented using nonstandard extensions, so long as those wrappers are provided by a designated project-wide portability header.

  - Nonstandard extensions do not work in all compilers. Use of nonstandard extensions reduces portability of code.
  - Even if they are supported in all targeted compilers, the extensions are often not well-specified, and there may be subtle behavior differences between compilers.
  - Nonstandard extensions add to the language features that a reader must know to understand the code.

## Further Reading

* [Google C++ Style Guide - Nonstandard Extensions](https://google.github.io/styleguide/cppguide.html#Nonstandard_Extensions)