Pattern: Assignment `Collections.sort()`

Issue: -

## Description

The `Collections.sort()` method mutates the list and returns the list as a value. If you are assigning the result of `sort()` to a variable, then you probably don't realize that you're also modifying the original list as well. This is frequently the cause of subtle bugs. This violation is triggered when a `sort()` method call appears as the right hand side of an assignment, or when it appears as the first method call in a series of chained method calls.

Example of violations:

``` groovy
  def a = someList.sort()
  def b = someList.sort() { it }
  def c = someList.sort().findAll { x < 1 }
```

## Further Reading

* [CodeNarc - AssignCollectionSort](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#AssignCollectionSort)