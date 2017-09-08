Pattern: Malformed final clause in `switch`

Issue: -

## Description

Checks whether the final clause of a switch statement ends in `break;`.

If no options are passed, a final `break;` is forbidden. If the `always` option is passed this will require a `break;` to always be present unless control flow is escaped in some other way.

## Further Reading

* [TSLint - switch-final-break](https://palantir.github.io/tslint/rules/switch-final-break)