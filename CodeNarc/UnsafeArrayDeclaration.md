Pattern: Unsafe array declaration

Issue: -

## Description

Triggers a violation when an array is declared `public`, `final`, and `static`.

In most cases an array declared `public`, `final`, and `static` is a bug. Because arrays are mutable objects, the final constraint requires that the array object itself be assigned only once, but makes no guarantees about the values of the array elements. Since the array is public, a malicious program can change the values stored in the array. In most situations the array should be made private.

Example of violations:

``` groovy
class SomeClass {
    public static final String[] someArray = init()
    public static final def someArray = [] as String[]
}
```

## Further Reading

* [CodeNarc - UnsafeArrayDeclaration](https://codenarc.github.io/CodeNarc/codenarc-rules-security.html#unsafearraydeclaration-rule)