Pattern: Malformed whitespace around `:`

Issue: -

## Description

This rule checks to see that there is spacing before and after the colon in a colon assignment (i.e., classes, objects). The spacing amount is specified by `spacing.left` and `spacing.right`, respectively. A zero value means no spacing required.

## Examples

``` coffeescript
#
# If spacing.left and spacing.right is 1
#


# Doesn't throw an error
object = {spacing : true}
class Dog
  canBark : true

  
# Throws an error
object = {spacing: true}
class Cat
  canBark: false
```

## Further Reading

* [CoffeeLint - colon_assignment_spacing](https://coffeelint.github.io/#options)