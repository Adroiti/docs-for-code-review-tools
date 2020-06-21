Pattern: Logging swallows stacktrace

Issue: -

## Description

If you are logging an exception then the proper API is to call `error(Object, Throwable)`, which will log the message and the exception stack trace. If you call `error(Object)` then the stacktrace may not be logged.

## Further Reading

* [CodeNarc - LoggingSwallowsStacktrace](https://codenarc.github.io/CodeNarc/codenarc-rules-logging.html#loggingswallowsstacktrace-rule)