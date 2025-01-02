Pattern: Use of duplicae variable

Issue: -

## Description

Disallow duplicate variables within a scope.

## Examples

```less
@a: 1;
@a: 2; // ✗ error
```

## Further Reading

* [stylelint-less](https://github.com/stylelint-less/stylelint-less/tree/main/packages/stylelint-less/src/rules/no-duplicate-variables)