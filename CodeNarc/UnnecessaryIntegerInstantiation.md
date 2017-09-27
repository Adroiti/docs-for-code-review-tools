Pattern: Unnecessary `Integer` instantiation

Issue: -

## Description

It is unnecessary to instantiate `Integer` objects. Instead just use the literal with the `I` identifier to force the type, such as `8I` or `42i`.

## Further Reading

* [CodeNarc - UnnecessaryIntegerInstantiation](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryIntegerInstantiation)