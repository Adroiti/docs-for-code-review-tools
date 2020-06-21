Pattern: Assignment of `Collections.unique()`

Issue: -

## Description

The `Collections.unique()` method mutates the list and returns the list as a value. If you are assigning the result of `unique()` to a variable, then you probably don't realize that you're also modifying the original list as well. This is frequently the cause of subtle bugs. This violation is triggered when a `unique()` method call appears as the right hand side of an assignment, or when it appears as the first method call in a series of chained method calls.

Example of violations:

``` groovy
  def a = someList.unique()
  def b = someList.unique() { it }
  def c = someList.unique().findAll { x < 1 }
```

## Further Reading

* [CodeNarc - AssignCollectionUnique](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#assigncollectionunique-rule)