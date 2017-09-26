Pattern: Use of `if` instead of ternary

Issue: -

## Description

Checks for:

-   An `if` statement where both the `if` and `else` blocks contain only a single `return` statement returning a constant or literal value.
-   A block where the second-to-last statement in a block is an `if` statement with no `else`, where the block contains a single `return` statement, and the last statement in the block is a `return` statement, and both `return` statements return a constant or literal value. This check is disabled by setting `checkLastStatementImplicitElse` to `false`.

Example of violations:

``` groovy
    if (condition) { return 44 } else { return 'yes' }                  // violation
    if (check()) { return [1, 2] } else { return "count=$count" }       // violation

    if (condition)                                                      // violation
        return null
    else return [a:1]

    def method1() {
        if (condition) {                                                // violation
            return 44
        }
        return 'yes'
    }
```

## Further Reading

* [CodeNarc - IfStatementCouldBeTernary](http://codenarc.sourceforge.net/codenarc-rules-convention.html#IfStatementCouldBeTernary)