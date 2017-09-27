Pattern: Unnecessary `Double` instantiation

Issue: -

## Description

It is unnecessary to instantiate `Double` objects. Instead just use the double literal with `'D` identifier to force the type, such as `123.45d` or `0.42d`.

## Further Reading

* [CodeNarc - UnnecessaryDoubleInstantiation](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryDoubleInstantiation)