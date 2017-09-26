Pattern: Catching `IllegalMonitorStateException`

Issue: -

## Description

Dubious catching of `IllegalMonitorStateException`. `IllegalMonitorStateException` is generally only thrown in case of a design flaw in your code (calling wait or notify on an object you do not hold a lock on).

## Further Reading

* [CodeNarc - CatchIllegalMonitorStateException](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#CatchIllegalMonitorStateException)