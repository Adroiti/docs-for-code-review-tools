Pattern: Malformed Unicode Byte Order Mark (BOM)

Issue: -

## Description

Require or disallow the Unicode Byte Order Mark.

## Examples

`string`: `"always"|"never"`

### `"always"`

The following pattern is considered a problem:

```css
a {}
```

The following pattern is _not_ considered a problem:

```css
U+FEFF
a {}
```

### `"never"`

The following pattern is considered a problem:

```css
U+FEFF
a {}
```

The following pattern is _not_ considered a problem:

```css
a {}
```

## Further Reading

* [stylelint - unicode-bom](https://stylelint.io/user-guide/rules/unicode-bom)