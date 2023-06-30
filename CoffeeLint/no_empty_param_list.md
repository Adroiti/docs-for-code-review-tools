Pattern: Empty function parameter list

Issue: -

## Description

This rule prohibits empty parameter lists in function definitions.

## Examples

``` coffeescript
# The empty parameter list in here is unnecessary:
someFunction = () ->


# We might favor this instead:
someFunction = ->
```

## Further Reading

* [CoffeeLint - no_empty_param_list](https://coffeelint.github.io/#options)