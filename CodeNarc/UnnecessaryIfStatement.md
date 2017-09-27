Pattern: Unnecessary `if` statement

Issue: -

## Description

Checks for unnecessary **if** statements. The entire **if** statement, or at least the *if* or *else* block, are considered unnecessary for the four scenarios described below.

(1) When the *if* and *else* blocks contain only an explicit return of `true` and `false` constants. These cases can be replaced by a simple *return* statement. Examples of violations include:

``` groovy
if (someExpression)         // can be replaced by: return someExpression
    return true
else
    return false

if (someExpression) {       // can be replaced by: return !someExpression
    return false
} else {
    return true
}

if (someExpression) {       // can be replaced by: return someExpression
    return Boolean.TRUE
} else {
    return Boolean.FALSE
}
```

(2) When the `if` statement is the last statement in a block and the *if* and *else* blocks are only `true` and `false` expressions. This is an *implicit* return of `true`/`false`. For example, the `if` statement in the following code can be replaced by `someExpression` or `someExpression as boolean`:

``` groovy
def someMethod() {
    doSomething()
    if (someExpression)
        true
    else false
}
```

(3) When the second-to-last statement in a block is an `if` statement with no `else`, where the block contains a single `return` statement, and the last statement in the block is a `return` statement, and one `return` statement returns a `true` expression and the other returns a `false` expression. This check is disabled by setting `checkLastStatementImplicitElse` to `false`. For example, the `if` statement in the following code can be replaced by `return expression1`:

``` groovy
def someMethod() {
    doSomething()
    if (expression1) {
        return true
    }
    return false
}
```

(4) When either the *if* block or *else* block of an `if` statement that is not the last statement in a block contain only a single constant or literal expression. For example, the `if` statement in the following code has no effect and can be removed:

``` groovy
def someMethod() {
    if (someExpression) { 123 }
    doSomething()
}
```

## Further Reading

* [CodeNarc - UnnecessaryIfStatement](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryIfStatement)