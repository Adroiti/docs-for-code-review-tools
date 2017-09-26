Pattern: Duplicate set value

Issue: -

## Description

A *Set* literal is created with duplicate constant value. A set cannot contain two elements with the same value.

Example of violations:

``` groovy
def a = [1, 2, 2, 4] as Set
def b = [1, 2, 2, 4] as HashSet
def c = [1, 2, 2, 4] as SortedSet
def d = [1, 2, 2, 4] as FooSet
def e = ['1', '2', '2', '4'] as Set
def f = ['1', '2', '2', '4'] as HashSet
def g = ['1', '2', '2', '4'] as SortedSet
def h = ['1', '2', '2', '4'] as FooSet

// these are OK
def a = [1, 2, 3, 4] as Set
def b = ['1', '2', '3', '4'] as Set
def c = [1, '1'] as Set
```

## Further Reading

* [CodeNarc - DuplicateSetValue](http://codenarc.sourceforge.net/codenarc-rules-basic.html#DuplicateSetValue)