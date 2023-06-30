Pattern: Implicit parentheses

Issue: -

## Description

This rule prohibits implicit parens on function calls.

## Examples

``` coffeescript
# Some folks don't like this style of coding.
someFunction a, b, c


# And would rather it always be written like this:
someFunction(a, b, c)
```

Implicit parens are permitted by default, since their use is idiomatic CoffeeScript.

## Further Reading

* [CoffeeLint - no_implicit_parens](https://coffeelint.github.io/#options)