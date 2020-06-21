Pattern: Use of `Throwable.printStackTrace()`

Issue: -

## Description

Checks for calls to `Throwable.printStackTrace()` or `StackTraceUtils.printSanitizedStackTrace(Throwable)`. Consider using a standard logging facility instead.

## Further Reading

* [CodeNarc - PrintStackTrace](https://codenarc.github.io/CodeNarc/codenarc-rules-logging.html#printstacktrace-rule)