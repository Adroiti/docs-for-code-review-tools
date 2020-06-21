Pattern: Static `DateFormat` field

Issue: -

## Description

`DateFormat` objects should not be used as `static` fields. DateFormats are inherently unsafe for multi-threaded use. Sharing a single instance across thread boundaries without proper synchronization will result in erratic behavior of the application. 

Under 1.4 problems seem to surface less often than under Java 5 where you will probably see random `ArrayIndexOutOfBoundsException` or `IndexOutOfBoundsException` in `sun.util.calendar.BaseCalendar.getCalendarDateFromFixedDate()`. You may also experience serialization problems. Using an instance field or a `ThreadLocal` is recommended.

Examples:

``` groovy
// Violations
class SomeClass {
    static DateFormat dateFormat1
    static java.text.DateFormat dateFormat2

    static final DATE1 = DateFormat.getDateInstance(DateFormat.LONG, Locale.FRANCE)
    static final def DATE2 = DateFormat.getDateInstance(DateFormat.LONG)
    static Object date3 = DateFormat.getDateInstance()

    static final DATETIME1 = DateFormat.getDateTimeInstance(DateFormat.LONG, DateFormat.SHORT, Locale.FRANCE)
    static final def DATETIME2 = DateFormat.getDateTimeInstance(DateFormat.LONG, DateFormat.SHORT)
    static final Object DATETIME3 = DateFormat.getDateTimeInstance()

    static final TIME1 = DateFormat.getTimeInstance(DateFormat.LONG, Locale.FRANCE)
    static final def TIME2 = DateFormat.getTimeInstance(DateFormat.LONG)
    static final Object TIME3 = DateFormat.getTimeInstance()
}

// These usages are OK
class SomeCorrectClass {
    private DateFormat calendar1
    static ThreadLocal<DateFormat> calendar2
}
```

## Further Reading

* [CodeNarc - StaticDateFormatField](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#staticdateformatfield-rule)