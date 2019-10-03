Pattern: Invalid Unicode BOM

Issue: -

## Description

Require or disallow the Unicode Byte Order Mark.

## Examples

### `"always"`

The following pattern is considered a violation:

```css
a {}
```

The following pattern is *not* considered a violation:

```css
U+FEFF
a {}
```

### `"never"`

The following pattern is considered a violation:

```css
U+FEFF
a {}
```

The following pattern is *not* considered a violation:

```css
a {}
```

## Further Reading

* [stylelint - unicode-bom](https://stylelint.io/user-guide/rules/unicode-bom)