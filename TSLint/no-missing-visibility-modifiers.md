Pattern: Missing visibility modifier

Issue: -

## Description

Deprecated - This rule is in the TSLint product as `member-access`.

Class members (both fields and methods) should have visibility modifiers
specified. The Principle of Least Visibility guides us to prefer private
methods and fields when possible. If a developer forgets to add a
modifier then TypeScript assumes the element should be public, which is
the wrong default choice.

## Further Reading

* [TSLint - no-missing-visibility-modifiers](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)