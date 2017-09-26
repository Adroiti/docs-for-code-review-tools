Pattern: Unnecessary Groovy import

Issue: -

## Description

Checks for an *import* from any package that is already automatically imported for Groovy files. A Groovy file does not need to include an import for classes from *java.lang*, *java.util*, *java.io*, *java.net*, *groovy.lang* and *groovy.util*, as well as the classes *java.math.BigDecimal* and *java.math.BigInteger*.

## Further Reading

* [CodeNarc - UnnecessaryGroovyImport](http://codenarc.sourceforge.net/codenarc-rules-imports.html#UnnecessaryGroovyImport)