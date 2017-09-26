Pattern: Returning `null` from `catch` block

Issue: -

## Description

Returning `null` from a `catch` block often masks errors and requires the client to handle error codes. In some coding styles this is discouraged. This rule ignores methods with `void` return type.

## Further Reading

* [CodeNarc - ReturnNullFromCatchBlock](http://codenarc.sourceforge.net/codenarc-rules-exceptions.html#ReturnNullFromCatchBlock)