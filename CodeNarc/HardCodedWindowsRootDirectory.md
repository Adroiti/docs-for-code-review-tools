Pattern: Hardcoded windows root directory

Issue: -

## Description

This rule find cases where a `File` object is constructed with a windows-based path. This is not portable across operating systems or different machines, and using the `File.listRoots()` method is a better alternative.

Example of violations:

``` groovy
new File('c:\\')
new File('c:\\dir')
new File('E:\\dir')
```

## Further Reading

* [CodeNarc - HardCodedWindowsRootDirectory](https://codenarc.github.io/CodeNarc/codenarc-rules-basic.html#hardcodedwindowsrootdirectory-rule)