Pattern: Missing use of `&&`/`||`

Issue: -

## Description

Usage of `&` in conditional statements is error-prone and inefficient. `condition` in `if (condition) expr` must always be length-1, in which case `&&` is to be preferred. Ditto for `|` vs. `||`.

Note that because `&` and `|` are generics, it is possible that `&&` / `||` are not perfect substitutes because `&` is doing method dispatch in an incompatible way.

Moreover, be wary of code that may have side effects, most commonly assignments. Consider `if ((a <- foo(x)) | (b <- bar(y))) { ... }` vs. `if ((a <- foo(x)) || (b <- bar(y))) { ... }`. Because `||` exits early, if `a` is `TRUE`,  the second condition will never be evaluated and `b` will not be assigned. Such usage is not allowed by the Tidyverse style guide, and the code can easily be refactored by pulling the assignment outside the condition, so using `||` is still preferable.

## Further Reading

* [lintr - Enforce usage of scalar logical operators in conditional statements](https://lintr.r-lib.org/reference/vector_logic_linter.html)