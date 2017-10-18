Pattern: Malformed arrow spacing

Issue: -

## Description

This rule checks to see that there is spacing before and after the arrow operator that declares a function.

## Examples

``` coffeescript
# Both of this will not trigger an error,
# even with arrow_spacing enabled.
x(-> 3)
x( -> 3)

# However, this will trigger an error
x((a,b)-> 3)
```

## Further Reading

* [CoffeeLint - arrow_spacing](http://www.coffeelint.org/#options)