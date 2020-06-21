Pattern: Static `Calendar` field

Issue: -

## Description

`Calendar` objects should not be used as `static` fields. Calendars are inherently unsafe for multi-threaded use. Sharing a single instance across thread boundaries without proper synchronization will result in erratic behavior of the application. 

Under 1.4 problems seem to surface less often than under Java 5 where you will probably see random `ArrayIndexOutOfBoundsException` or `IndexOutOfBoundsException` in `sun.util.calendar.BaseCalendar.getCalendarDateFromFixedDate()`. You may also experience serialization problems. Using an instance field or a `ThreadLocal` is recommended.

Examples:

``` groovy
// Violations
class SomeClass {
    static Calendar calendar1
    static java.util.Calendar calendar2

    static final CAL1 = Calendar.getInstance()
    static final CAL2 = Calendar.getInstance(Locale.FRANCE)
    static def cal3 = Calendar.getInstance(timezone)
    static Object cal4 = Calendar.getInstance(timezone, locale)
}

// These usages are OK
class SomeCorrectClass {
    private final Calendar calendar1
    static ThreadLocal<Calendar> calendar2
}
```

## Further Reading

* [CodeNarc - StaticCalendarField](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#staticcalendarfield-rule)