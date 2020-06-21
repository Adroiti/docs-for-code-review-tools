Pattern: Volatile array field

Issue: -

## Description

Volatile array fields are unsafe because the contents of the array are not treated as volatile. Changing the entire array reference is visible to other threads, but changing an array element is not.

Example of violations:

``` groovy
class SomeClass {
    private volatile Object[] field1 = value()
    volatile field2 = value as Object[]
    volatile field3 = (Object[])foo
}
```

## Further Reading

* [SlideShare - Java Concurrency Gotchas](https://www.slideshare.net/alexmiller/java-concurrency-gotchas-3666977)
* [CodeNarc - VolatileArrayField](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#volatilearrayfield-rule)