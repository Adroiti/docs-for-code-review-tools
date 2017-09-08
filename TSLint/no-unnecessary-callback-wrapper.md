Pattern: No unnecessary callback wrapper

Issue: -

## Description

Replaces `x => f(x)` with just `f`. To catch more cases, enable `only-arrow-functions` and `arrow-return-shorthand` too.

## Further Reading

* [TSLint - no-unnecessary-callback-wrapper](https://palantir.github.io/tslint/rules/no-unnecessary-callback-wrapper)