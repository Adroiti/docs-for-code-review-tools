Pattern: Malformed indentation

Issue: -

## Description

This rule imposes a standard number of spaces to be used for indentation. Since whitespace is significant in CoffeeScript, it's critical that a project chooses a standard indentation format and stays consistent.

## Examples

``` coffeescript
 #
Enabling this option will prevent this ugly
# but otherwise valid CoffeeScript.
twoSpaces = () ->
  fourSpaces = () ->
      eightSpaces = () ->
            'this is valid CoffeeScript'

```

Two space indentation is enabled by default.

## Further Reading

* [CoffeeLint - indentation](https://coffeelint.github.io/#options)