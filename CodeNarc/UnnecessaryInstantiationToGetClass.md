Pattern: Unnecessary instantiation to `getClass()`

Issue: -

## Description

Avoid instantiating an object just to call `getClass()` on it; use the `.class` public member instead.

``` groovy
public class Foo {
 // Replace this
 Class c = new String().getClass();

 // with this:
 Class c = String.class;
}
```

## Further Reading

* [CodeNarc - UnnecessaryInstantiationToGetClass](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessaryinstantiationtogetclass-rule)