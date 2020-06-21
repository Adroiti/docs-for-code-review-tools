Pattern: Use of `notify()`

Issue: -

## Description

Checks for code that calls `notify()` rather than `notifyAll()`. Java monitors are often used for multiple conditions. Calling `notify()` only wakes up one thread, meaning that the awakened thread might not be the one waiting for the condition that the caller just satisfied.

## Further Reading

* [CodeNarc - UseOfNotifyMethod](https://codenarc.github.io/CodeNarc/codenarc-rules-concurrency.html#useofnotifymethod-rule)