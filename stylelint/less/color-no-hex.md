Pattern: Use of hex color

Issue: -

## Description

Disallow the usage of hex colors.

## Examples

```less
a { color: #fff; } // ✗ avoid

a { color: red; } // ✓ ok
```

## Further Reading

* [stylelint-less](https://github.com/stylelint-less/stylelint-less/tree/main/packages/stylelint-less/src/rules/color-no-hex)