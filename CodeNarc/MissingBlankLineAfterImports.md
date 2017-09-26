Pattern: Missing blank line after imports

Issue: -

## Description

Makes sure there is a blank line after the imports of a source code file.

Example of violation:

``` groovy
import org.apache.commons.lang.StringUtils
class MyClass { }                       // violation
```

## Further Reading

* [CodeNarc - MissingBlankLineAfterImports](http://codenarc.sourceforge.net/codenarc-rules-formatting.html#MissingBlankLineAfterImports)