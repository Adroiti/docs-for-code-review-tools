Pattern: Missing use of object shorthand

Issue: -

## Description

Use property value shorthand in objects, when explicit braces are used.

## Examples

``` coffeescript
test = "value"

# Good
{test}
test: test

# Bad
{test: test}
```

## Further Reading

* [CoffeeLint - object_shorthand](https://coffeelint.github.io/#options)