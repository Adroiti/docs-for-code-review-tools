Pattern: Exception not thrown

Issue: -

## Description

Checks for an exception constructor call without a `throw` as the last statement within a catch block. This rule treats any constructor call for a class named `xxxException` as an exception constructor call.

Example of violations:

``` groovy
void execute() {
    try { } catch(Exception e) { new Exception(e) }     // violation
}

try {
    doStuff()
} catch(DaoException e) {
    log.warning("Ooops", e)
    new ServiceException(e)                             // violation
} catch(Exception e) {
    new SystemException(e)                              // violation
}

try {
    doStuff()
} catch(Exception e) { throw new DaoException(e) }      // ok
```

## Further Reading

* [CodeNarc - ExceptionNotThrown](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#ExceptionNotThrown)