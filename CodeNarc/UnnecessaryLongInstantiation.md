Pattern: Unnecessary `Long` instantiation

Issue: -

## Description

It is unnecessary to instantiate `Long` objects. Instead just use the literal with the `L` identifier to force the type, such as `8L` or `42L`.

## Further Reading

* [CodeNarc - UnnecessaryLongInstantiation](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryLongInstantiation)