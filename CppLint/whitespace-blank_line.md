Pattern: Malformed whitespace

Issue: -

## Description

Don't use blank lines when you don't have to. In particular, don't put more than one or two blank lines between functions, resist starting functions with a blank line, don't end functions with a blank line, and be discriminating with your use of blank lines inside functions.

The basic principle is: The more code that fits on one screen, the easier it is to follow and understand the control flow of the program. Of course, readability can suffer from code being too dense as well as too spread out, so use your judgement. But in general, minimize use of vertical whitespace.

Some rules of thumb to help when blank lines may be useful:

  - Blank lines at the beginning or end of a function very rarely help readability.
  - Blank lines inside a chain of if-else blocks may well help readability.
  
  
## Further Reading

* [Google C++ Style Guide - Vertical Whitespace](https://google.github.io/styleguide/cppguide.html#Vertical_Whitespace)

