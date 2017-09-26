Pattern: Misordered static import

Issue: -

## Description

Checks for static import statements which should never be after non-static imports. This rule has one property `comesBefore`, which defaults to `true`. If you like your static imports to come after the others, then set this property to false.

Examples of violations:

``` groovy
import my.something.another
import static foo.bar

public class MyClass{}
```

## Further Reading

* [CodeNarc - MisorderedStaticImports](http://codenarc.sourceforge.net/codenarc-rules-imports.html#MisorderedStaticImports)