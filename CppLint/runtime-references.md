Pattern: Non-const reference

Issue: -

## Description

Within function parameter lists all references must be `const`:
    
    
    void Foo(const string &in, string *out);
    

In fact it is a very strong convention in Google code that input arguments are values or `const` references while output arguments are pointers. Input parameters may be `const` pointers, but we never allow non-`const` reference parameters except when required by convention, e.g., `swap()`.

However, there are some instances where using `const T*` is preferable to `const T&` for input parameters. For example:

  - You want to pass in a null pointer.
  - The function saves a pointer or reference to the input.

Remember that most of the time input parameters are going to be specified as `const T&`. Using `const T*` instead communicates to the reader that the input is somehow treated differently. So if you choose `const T*` rather than `const T&`, do so for a concrete reason; otherwise it will likely confuse readers by making them look for an explanation that doesn't exist.


## Further Reading

* [Google C++ Style Guide - Reference Arguments](https://google.github.io/styleguide/cppguide.html#Reference_Arguments)