Pattern: Use of restricted vendor prefix for at-rule

Issue: -

## Description

Disallow vendor prefixes for at-rules.

## Examples

The following patterns are considered violations:

```css
    @-webkit-keyframes { 0% { top: 0; } }
/**  ↑
 * These prefixes */
```

```css
@-ms-viewport { orientation: landscape; }
```

The following patterns are *not* considered violations:

```css
@keyframes { 0% { top: 0; } }
```

```css
@viewport { orientation: landscape; }
```

## Further Reading

* [stylelint - at-rule-no-vendor-prefix](https://stylelint.io/user-guide/rules/at-rule-no-vendor-prefix)