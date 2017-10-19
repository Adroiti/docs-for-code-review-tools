Pattern: Unexpected vendor-prefix value

Issue: -

## Description

This rule will only complain for prefixed *standard* values, and not for prefixed *proprietary* or *unknown* ones.

## Examples

The following patterns are considered violations:

```css
a { display: -webkit-flex; }
/**          ↑
 *  These prefixes */
```

```css
a { max-width: -moz-max-content; }
```

```css
a { background: -webkit-linear-gradient(bottom, #000, #fff); }
```

The following patterns are *not* considered violations:

```css
a { display: flex; }
```

```css
a { max-width: max-content; }
```

```css
a { background: linear-gradient(bottom, #000, #fff); }
```

## Further Reading

* [stylelint - value-no-vendor-prefix](https://stylelint.io/user-guide/rules/value-no-vendor-prefix)