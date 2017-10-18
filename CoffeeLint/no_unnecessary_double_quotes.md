Pattern: Unnecessary double quotes

Issue: -

## Description

This rule prohibits double quotes unless string interpolation is used or the string contains single quotes.

## Examples

``` coffeescript
# Double quotes are discouraged:
foo = "bar"

# Unless string interpolation is used:
foo = "#{bar}baz"

# Or they prevent cumbersome escaping:
foo = "I'm just following the 'rules'"
```

## Further Reading

* [CoffeeLint - no_unnecessary_double_quotes](http://www.coffeelint.org/#options)