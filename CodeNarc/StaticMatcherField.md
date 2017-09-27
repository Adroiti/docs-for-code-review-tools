Pattern: Static `Matcher` field

Issue: -

## Description

`Matcher` objects should not be used as static fields. Calendars are inherently unsafe for multi-threaded use. Sharing a single instance across thread boundaries without proper synchronization will result in erratic behavior of the application.

Example of violations:

``` groovy
// two violations
class SomeClass {
  static Matcher matcher1
  static java.util.regex.Matcher matcher2
}

// these usages are OK
class SomeCorrectClass {
  private Matcher matcher1
  static ThreadLocal<Matcher> matcher2
}
```

## Further Reading

* [CodeNarc - StaticMatcherField](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#StaticMatcherField)