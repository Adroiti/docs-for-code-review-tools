Pattern: Missing blank line after `package`

Issue: -

## Description

Makes sure there is a blank line after the `package` statement of a source code file.

Example of violation:

``` groovy
  package org.codenarc
  import java.util.Date                     // violation

  class SomeClass {
  void go() { /* ... */ }
  }
```

## Further Reading

* [CodeNarc - MissingBlankLineAfterPackage](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#missingblanklineafterpackage-rule)