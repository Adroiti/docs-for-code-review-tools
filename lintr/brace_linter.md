Pattern: Malformed curly brace

Issue: -

## Description

Performs various style checks related to placement and spacing of curly braces.

Details

    Opening curly braces are never on their own line and are always followed by a newline.

    Opening curly braces have a space before them.

    Closing curly braces are on their own line unless they are followed by an `else`.

    Closing curly braces in `if` conditions are on the same line as the corresponding `else`.

    Either both or neither branch in `if`/`else` use curly braces, i.e., either both branches use `{...}` or neither does.

    Functions spanning multiple lines use curly braces.


## Further Reading

* [lintr - Brace linter](https://lintr.r-lib.org/reference/brace_linter.html)