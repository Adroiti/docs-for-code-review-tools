Pattern: Use of Mocha's `*.only` function

Issue: -

## Description

Do not invoke Mocha's `describe.only`, `it.only`, or `context.only`
functions. These functions are useful ways to run a single unit test or
a single test case during your build, but please be careful to not push
these methods calls to your version control repository because it will
turn off any of the other tests.

## Further Reading

* [TSLint - mocha-avoid-only](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)