Pattern: JUnit - `fail()` without message

Issue: -

## Description

This rule detects JUnit calling the `fail()` method without an argument. For better error reporting you should always provide a message.

## Further Reading

* [CodeNarc - JUnitFailWithoutMessage](https://codenarc.github.io/CodeNarc/codenarc-rules-junit.html#junitfailwithoutmessage-rule)