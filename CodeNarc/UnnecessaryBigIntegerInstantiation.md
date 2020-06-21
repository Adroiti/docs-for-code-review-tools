Pattern: Unnecessary `BigInteger` instantiation

Issue: -

## Description

It is unnecessary to instantiate `BigInteger` objects. Instead just use the literal with the `G` identifier to force the type, such as `8G` or `42G`.

## Further Reading

* [CodeNarc - UnnecessaryBigIntegerInstantiation](https://codenarc.github.io/CodeNarc/codenarc-rules-unnecessary.html#unnecessarybigintegerinstantiation-rule)