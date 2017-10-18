Pattern: Nested string interpolation

Issue: -

## Description

This rule warns about nested string interpolation, as it tends to make code harder to read and understand.

## Examples

``` coffeescript
# Good!
str = "Book by #{firstName.toUpperCase()} #{lastName.toUpperCase()}"

# Bad!
str = "Book by #{"#{firstName} #{lastName}".toUpperCase()}"
```

## Further Reading

* [CoffeeLint - no_nested_string_interpolation](http://www.coffeelint.org/#options)