Pattern: Trailing `;`

Issue: -

## Description

This rule prohibits trailing semicolons, since they are needless cruft in CoffeeScript.

## Examples

``` coffeescript
# This semicolon is meaningful.
x = '1234'; console.log(x)

# This semicolon is redundant.
alert('end of line');
```

## Further Reading

* [CoffeeLint - no_trailing_semicolons](http://www.coffeelint.org/#options)