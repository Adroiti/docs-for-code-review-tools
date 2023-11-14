Pattern: Malformed CSS syntax

Issue: -

## Description

This rule examinate CSS syntax. It checks at-rules and declaration values to match W3C specs and browsers extensions.

## Examples

The following patterns are considered violations:

```css
.first { color: red green }

.second { color: 1 }
```

The following patterns are *not* considered violations:

```css
.first { color: red }

.second { color: #123456 }
```

## Further Reading

* [stylelint-validator](https://github.com/csstree/stylelint-validator)