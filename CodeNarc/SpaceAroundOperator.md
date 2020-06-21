Pattern: Malformed space around operator

Issue: -

## Description

Checks that there is at least one space (blank) or whitespace around each binary operator, including: +, -, \*, /, &gt;&gt;, &lt;&lt;, &&, ||, &, |, ?:, =, "as".

Does not check dot ('.') operator. Does not check unary operators (!, +, -, ++, --, ?.). Does not check array ('\[') operator.

Known limitations:

-   Does not catch violations of missing space around equals operator (=) within a declaration expression, e.g. `def x=23`
-   Does not catch violations of certain ternary expressions and standalone elvis operator (?:) expressions

Examples of violations:

``` groovy
def someMethod() {
    3+ 5-x*23/ 100              // violation
    list \<\<123                // violation
    other\>\> writer            // violation
    x=99                        // violation
    x&& y                       // violation
    x ||y                       // violation
    x &y                        // violation
    x| y                        // violation
    [1,2]as String              // violation
}
```

## Further Reading

* [CodeNarc - SpaceAroundOperator](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#spacearoundoperator-rule)