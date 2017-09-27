Pattern: Static `SimpleDateFormat` field

Issue: -

## Description

`SimpleDateFormat` objects should not be used as `static` fields. SimpleDateFormats are inherently unsafe for multi-threaded use. Sharing a single instance across thread boundaries without proper synchronization will result in erratic behavior of the application. 

Under 1.4 problems seem to surface less often than under Java 5 where you will probably see random `ArrayIndexOutOfBoundsException` or `IndexOutOfBoundsException` in `sun.util.calendar.BaseCalendar.getCalendarDateFromFixedDate()`. You may also experience serialization problems. Using an instance field or a `ThreadLocal` is recommended.

Examples:

``` groovy
// Violations
class SomeClass {
    static SimpleDateFormat dateFormat1
    static java.text.SimpleDateFormat dateFormat2

    static final DATE1 = new SimpleDateFormat()
    static final DATE2 = new SimpleDateFormat('MM/dd')
    static final DATE3 = new SimpleDateFormat('MM/dd', DateFormatSymbols.instance)
    static date4 = new SimpleDateFormat('MM/dd', Locale.FRANCE)
    static date5 = new java.text.SimpleDateFormat('MM/dd')
}

// These usages are OK
class SomeCorrectClass {
    private SimpleDateFormat calendar1
    static ThreadLocal<SimpleDateFormat> calendar2
}
```

## Further Reading

* [CodeNarc - StaticSimpleDateFormatField](http://codenarc.sourceforge.net/codenarc-rules-concurrency.html#StaticSimpleDateFormatField)