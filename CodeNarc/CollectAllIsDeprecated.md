Pattern: Use of deprecated `collectAll()`

Issue: -

## Description

The `collectAll` method is deprecated since Groovy 1.8.1. Use `collectNested` instead.

Example of violations:

``` groovy
def list = [1, 2, [3, 4, [5, 6]], 7]

list.collectAll { it * 2 }      // deprecated

list.collectNested { it * 2 }   // replacement
```

## Further Reading

* [CodeNarc - CollectAllIsDeprecated](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#collectallisdeprecated-rule)