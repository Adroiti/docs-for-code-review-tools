Pattern: Hardcoded windows file separator

Issue: -

## Description

This rule finds usages of a Windows file separator within the constructor call of a `File` object. It is better to use the Unix file separator or use the `File.separator` constant.

Example of violations:

``` groovy
new File('.\\foo\\')
new File('c:\\dir')
new File('../foo\\')
```

## Further Reading

* [CodeNarc - Hard coded windows file separator](http://codenarc.sourceforge.net/codenarc-rules-basic.html#HardCodedWindowsFileSeparator)