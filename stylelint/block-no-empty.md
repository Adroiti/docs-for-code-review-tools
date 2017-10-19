Pattern: Empty block

Issue: -

## Description

Disallow empty blocks.

## Examples

The following patterns are considered violations:

```css
 a { }
/** ↑
 * Blocks like this */
```

```css
a {}
```

```css
@media print { a {} }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
@media print { a { color: pink; } }
```

## Further Reading

* [stylelint - block-no-empty](https://stylelint.io/user-guide/rules/block-no-empty)