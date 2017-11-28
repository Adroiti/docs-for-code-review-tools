Pattern: Unnecessary class

Issue: -

## Description

Disallows classes that are not strictly necessary. Users who come from a Java-style OO language may wrap their utility functions in an extra class, instead of putting them at the top level.

## Configuration

Three arguments may be optionally provided:

* `"allow-constructor-only"` ignores classes whose members are constructors.
* `"allow-empty-class"` ignores class `DemoClass {}`.
* `"allow-static-only"` ignores classes whose members are static.

## Further Reading

* [TSLint - no-unnecessary-class](https://palantir.github.io/tslint/rules/no-unnecessary-class)