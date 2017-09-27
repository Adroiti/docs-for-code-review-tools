Pattern: Wildcard import

Issue: -

## Description

Wildcard imports, static or otherwise, should not be used.

Example of violations:

``` groovy
import some.something.*
import static foo.bar.*

public class SomeClass{}
```

## Further Reading

* [CodeNarc - NoWildcardImports](http://codenarc.sourceforge.net/codenarc-rules-imports.html#NoWildcardImports)