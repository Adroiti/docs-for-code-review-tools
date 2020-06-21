Pattern: Unnecessary call for last element

Issue: -

## Description

This rule checks for excessively verbose methods of accessing the last element of an array or list. For instance, it is possible to access the last element of an array by performing `array[array.length - 1]`, in Groovy it is simpler to either call `array.last()` or `array[-1]`. The same is true for lists. This violation is triggered whenever a `get`, `getAt`, or array-style access is used with an object size check.

Code like this all cause violations:

``` groovy
def x = [0, 1, 2]
def a = x.get(x.size() -1)
def b = x.get(x.length -1)
def c = x.getAt(x.size() -1)
def d = x.getAt(x.length -1)
def f = x[(x.size() -1]
def d = x[(x.length -1]
```

All of this code is fine though:

``` groovy
def x = [0, 1, 2]
def a = x.last()
def b = x[-1]
def c = x.getAt(-1)
def d = x.get(z.size() -1)     // different objects
def e = x.get(z.length -1)     // different objects
def f = x.getAt(z.size() -1)   // different objects
```

## Further Reading

* [CodeNarc - UnnecessaryCallForLastElement](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarycallforlastelement-rule)