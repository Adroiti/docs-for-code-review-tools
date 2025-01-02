Pattern: Inconsistent hex color

Issue: -

## Description

Specify lowercase or uppercase for hex colors.

## Examples

### lower

```less
a { color: #fff; } // ✓ ok
a { color: #FFF; } // ✗ error
```

### upper

```less
a { color: #FFF; } // ✓ ok
a { color: #fff; } // ✗ error
```

## Further Reading

* [stylelint-less](https://github.com/stylelint-less/stylelint-less/blob/main/packages/stylelint-less/src/rules/color-hex-case/README.md)