Pattern: Misuse of `#define` Guard

Issue: -

## Description

All header files should have `#define` guards to prevent multiple inclusion. The format of the symbol name should be `_<PROJECT>___<PATH>___<FILE>__H_`.

To guarantee uniqueness, they should be based on the full path in a project's source tree. For example, the file `foo/src/bar/baz.h` in project `foo` should have the following guard:
    
    
    #ifndef FOO_BAR_BAZ_H_
    #define FOO_BAR_BAZ_H_

    ...

    #endif  // FOO_BAR_BAZ_H_

	
## Further Reading

* [Google C++ Style Guide - The #define Guard](https://google.github.io/styleguide/cppguide.html#The__define_Guard)
	