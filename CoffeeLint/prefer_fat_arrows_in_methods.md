Pattern: Missing use of fat arrow

Issue: -

## Description

Warns when you do not use a fat arrow for functions defined inside
method bodies. This assures that `this` is always bound to the
method's object inside the code block of a method.

## Further Reading

* [CoffeeLint - prefer_fat_arrows_in_methods](https://coffeelint.github.io/#options)