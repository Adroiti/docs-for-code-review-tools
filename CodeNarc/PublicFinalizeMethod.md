Pattern: Public `finalize()` method

Issue: -

## Description

Creates a violation when the program violates secure coding principles by declaring a `finalize()` method public.

A program should never call finalize explicitly, except to call `super.finalize()` inside an implementation of `finalize()`. In mobile code situations, the otherwise error prone practice of manual garbage collection can become a security threat if an attacker can maliciously invoke one of your `finalize()` methods because it is declared with public access. If you are using `finalize()` as it was designed, there is no reason to declare `finalize()` with anything other than protected access.

## Further Reading

* [CodeNarc - PublicFinalizeMethod](http://codenarc.sourceforge.net/codenarc-rules-security.html#PublicFinalizeMethod)