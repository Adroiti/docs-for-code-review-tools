Pattern: Empty function

Issue: -

## Description

Disallows declaring empty functions. The goal of this rule is that unintentional empty callbacks can be detected:

``` coffeescript
someFunctionWithCallback ->
doSomethingSignificant()
```

The problem is that the call to `doSomethingSignificant` will be made regardless of `someFunctionWithCallback`'s execution. It can be because you did not indent the call to `doSomethingSignificant` properly. If you really meant that `someFunctionWithCallback` should call a callback that does nothing, you can write your code this way:

``` coffeescript
someFunctionWithCallback ->
    undefined
doSomethingSignificant()
```

## Further Reading

* [CoffeeLint - no_empty_functions](https://coffeelint.github.io/#options)