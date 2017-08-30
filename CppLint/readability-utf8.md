Pattern: Invalid UTF-8 or replacement character

Issue: -

## Description

Line contains invalid UTF-8 or Unicode replacement character.

Use the `u8` prefix to guarantee that a string literal containing `\uXXXX` escape sequences is encoded as UTF-8. Do not use it for strings containing non-ASCII characters encoded as UTF-8, because that will produce incorrect output if the compiler does not interpret the source file as UTF-8. 


## Further Reading

* [Google C++ Style Guide - Non-ASCII Characters](https://google.github.io/styleguide/cppguide.html#Non-ASCII_Characters)