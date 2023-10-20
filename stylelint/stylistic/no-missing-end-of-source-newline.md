Pattern: Missing end-of-source newline

Issue: -

## Description

Disallow missing end-of-source newlines. Completely empty files are not considered violations.

## Examples

The following patterns are considered violations:

```css
a { color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
\n
```

## Further Reading

* [stylelint - no-missing-end-of-source-newline](https://stylelint.io/user-guide/rules/no-missing-end-of-source-newline)