Pattern: Method overloaded too many times

Issue: -

## Description

Method overloading tightly couples these methods together which might make the code harder to understand. 

Refactor these methods and try to use optional parameters instead to prevent some of the overloading.

## Further Reading

* [Detekt - MethodOverloading](https://detekt.dev/docs/rules/complexity/#methodoverloading)