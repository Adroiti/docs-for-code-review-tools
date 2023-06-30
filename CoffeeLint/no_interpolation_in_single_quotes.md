Pattern: Interpolation in single quotes

Issue: -

## Description

This rule prohibits string interpolation in a single quoted string.

## Examples

``` coffeescript
# String interpolation in single quotes is not allowed:
foo = '#{bar}'


# Double quotes is OK of course
foo = "#{bar}"
```

## Further Reading

* [CoffeeLint - no_interpolation_in_single_quotes](https://coffeelint.github.io/#options)