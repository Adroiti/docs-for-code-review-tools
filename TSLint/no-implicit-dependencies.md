Pattern: Unexpected module dependency

Issue: -

## Description

Disallows importing modules that are not listed as dependency in the project’s package.json

Disallows importing transient dependencies and modules installed above your package’s root directory.

## Configuration

By default the rule looks at `"dependencies"` and `"peerDependencies"`. By adding the `"dev"` option the rule looks at `"devDependencies"` instead of `"peerDependencies"`. By adding the `"optional"` option the rule also looks at `"optionalDependencies"`.

## Further Reading

* [TSLint - no-implicit-dependencies](https://palantir.github.io/tslint/rules/no-implicit-dependencies)