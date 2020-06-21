Pattern: Malformed brace for class

Issue: -

## Description

Checks the location of the opening brace (`{`) for classes. By default, requires them on the same line, but the `sameLine` property can be set to `false` to override this.

NOTE: This rule ignores annotation types, e.g. `@interface SomeAnnotation `.

## Further Reading

* [CodeNarc - BracesForClass](https://codenarc.github.io/CodeNarc/codenarc-rules-formatting.html#bracesforclass-rule)