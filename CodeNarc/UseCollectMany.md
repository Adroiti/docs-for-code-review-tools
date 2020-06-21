Pattern: Use of `collect.flatten()`

Issue: -

## Description

In many cases `collectMany()` yields the same result as `collect.flatten()`. It is easier to understand and more clearly conveys the intent.

Example of violations:

``` groovy
def l = [1, 2, 3, 4]

l.collect{ [it, it*2] }.flatten() // suboptimal

l.collectMany{ [it, it*2] }       // same functionality, better readability
```

## Further Reading

* [CodeNarc - UseCollectMany](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#usecollectmany-rule)