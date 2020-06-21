Pattern: Unnecessary ternary expression

Issue: -

## Description

Checks for ternary expressions where the conditional expression always evaluates to a boolean and the *true* and *false* expressions are merely returning `true` and `false` constants. These cases can be replaced by a simple boolean expression. Examples of violations include:

``` groovy
x==99 ? true : false                    // can be replaced by: x==99
x && y ? true : false                   // can be replaced by: x && y
x||y ? false : true                     // can be replaced by: !(x||y)
x >= 1 ? true: false                    // can be replaced by: x >= 1
x < 99 ? Boolean.TRUE : Boolean.FALSE   // can be replaced by: x < 99
!x ? true : false                       // can be replaced by: !x
```

The rule also checks for ternary expressions where the *true* and *false* expressions are the same constant or variable. Examples include:

``` groovy
x ? '123' : '123'              // can be replaced by: '123'
x ? null : null                // can be replaced by: null
x ? 23 : 23                    // can be replaced by: 23
x ? MAX_VALUE : MAX_VALUE      // can be replaced by: MAX_VALUE
ready ? minValue : minValue    // can be replaced by: minValue
```

## Further Reading

* [CodeNarc - UnnecessaryTernaryExpression](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessaryternaryexpression-rule)