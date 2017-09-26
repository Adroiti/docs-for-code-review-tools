Pattern: Volatile `long` or `double` field

Issue: -

## Description

This rule reports on `long` or `double` fields that are declared `volatile`.

Long or double fields should not be declared as `volatile`. Java specifies that reads and writes from such fields are atomic, but many JVM's have violated this specification. Unless you are certain of your JVM, it is better to synchronize access to such fields rather than declare them `volatile`. This rule flags fields marked `volatile` when their type is `double` or `long` or the name of their type is `Double` or `Long`.

Here is an example of code that produces a violation:

``` groovy
 def method() {
     private volatile double d
     private volatile long f
 }
```

## Further Reading

* [CodeNarc - VolatileLongOrDoubleField](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#VolatileLongOrDoubleField)