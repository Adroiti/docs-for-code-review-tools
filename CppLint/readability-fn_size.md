Pattern: Long function

Issue: -

## Description

Prefer small and focused functions. If a function exceeds about 40 lines, think about whether it can be broken up without harming the structure of the program.

Even if your long function works perfectly now, someone modifying it in a few months may add new behavior. This could result in bugs that are hard to find. Keeping your functions short and simple makes it easier for other people to read and modify your code.

## Further Reading

* [Google C++ Style Guide - Write Short Functions](https://google.github.io/styleguide/cppguide.html#Write_Short_Functions)