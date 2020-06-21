Pattern: Confusing method name

Issue: -

## Description

Checks for very confusing method names. The referenced methods have names that differ only by capitalization. This is very confusing because if the capitalization were identical then one of the methods would override the other.

Also, violations are triggered when methods and fields have very similar names.

``` groovy
class SomeClass {
    int total
    int total() {
        1
    }
}
```

## Further Reading

* [CodeNarc - ConfusingMethodName](https://codenarc.github.io/CodeNarc/codenarc-rules-naming.html#confusingmethodname-rule)