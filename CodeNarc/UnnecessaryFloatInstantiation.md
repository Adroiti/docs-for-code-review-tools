Pattern: Unnecessary `Float` instantiation

Issue: -

## Description

It is unnecessary to instantiate `Float` objects. Instead just use the float literal with the `F` identifier to force the type, such as `123.45F` or `0.42f`.

## Further Reading

* [CodeNarc - UnnecessaryFloatInstantiation](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessaryfloatinstantiation-rule)