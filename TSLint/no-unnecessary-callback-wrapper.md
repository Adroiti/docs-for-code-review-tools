Pattern: Unnecessary callback wrapper

Issue: -

## Description

Replace `x => f(x)` with just `f`. To catch more cases, enable `only-arrow-functions` and `arrow-return-shorthand` too.

## Further Reading

* [TSLint - no-unnecessary-callback-wrapper](https://palantir.github.io/tslint/rules/no-unnecessary-callback-wrapper)