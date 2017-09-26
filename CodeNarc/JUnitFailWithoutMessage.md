Pattern: JUnit - `fail()` without message

Issue: -

## Description

This rule detects JUnit calling the `fail()` method without an argument. For better error reporting you should always provide a message.

## Further Reading

* [CodeNarc - JUnitFailWithoutMessage](http://codenarc.sourceforge.net/codenarc-rules-junit.html#JUnitFailWithoutMessage)