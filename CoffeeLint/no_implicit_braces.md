Pattern: Implicit braces

Issue: -

## Description

This rule prohibits implicit braces when declaring object literals. Implicit braces can make code more difficult to understand, especially when used in combination with optional parenthesis.

## Examples

``` coffeescript
# Do you find this code ambiguous? Is it a
# function call with three arguments or four?
someFunction a, b, 1:2, 3:4


# While the same code written in a more
# explicit manner has no ambiguity.
someFunction(a, b, {1:2, 3:4})
```

Implicit braces are permitted by default, since their use is idiomatic CoffeeScript.

## Further Reading

* [CoffeeLint - no_implicit_braces](https://coffeelint.github.io/#options)