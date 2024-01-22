Pattern: Use of unknown function

Issue: -

## Description

Considers functions defined in the CSS Specifications to be known.

This rule ignores double-dashed custom functions, e.g. `--custom-function()`.

## Examples

The following patterns are considered violations:

```css
a { transform: unknown(1); }
```

The following patterns are *not* considered violations:

```css
a { transform: scale(1); }
```

```css
a { transform: --custom-function(1); }
```

## Further Reading

* [stylelint - function-no-unknown](https://stylelint.io/user-guide/rules/list/function-no-unknown)