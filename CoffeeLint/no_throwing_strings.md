Pattern: Throwing plain string

Issue: -

## Description

This rule forbids throwing string literals or interpolations. While JavaScript (and CoffeeScript by extension) allow any expression to be thrown, it is best to only throw `Error` objects, because they contain valuable debugging information like the stack trace. 

Because of JavaScript's dynamic nature, CoffeeLint cannot ensure you are always throwing instances of `Error`. It will only catch the simple but real case of throwing literal strings.

## Examples

``` coffeescript
# CoffeeLint will catch this:
throw "error text"


# ... but not this:
throw getSomeString()
```

## Further Reading

* [CoffeeLint - no_throwing_strings](http://www.coffeelint.org/#options)