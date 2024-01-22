Pattern: Malformed whitespace after `;` of declaration block

Issue: -

## Description

Require a single space or disallow whitespace after the semicolons of declaration blocks. This rule ignores semicolons that are preceded by Less mixins.

This rule ignores the last semicolon of declaration blocks. Use the `block-closing-brace-*-before` rules to control the whitespace between the last semicolon and the closing brace instead.

## Examples

### `"always"`

There *must always* be a single space after the semicolon.

The following patterns are considered violations:

```css
a { color: pink;top: 0; }
```

```css
a {
  color: pink;
  top: 0;
}
```

The following patterns are *not* considered violations:

```css
a { color: pink;}
```

```css
a { color: pink; }
```

```css
a { color: pink; top: 0; }
```

### `"never"`

There *must never* be whitespace after the semicolon.

The following patterns are considered violations:

```css
a { color: pink; top: 0; }
```

```css
a {
  color: pink;
  top: 0;
}
```

The following patterns are *not* considered violations:

```css
a { color: pink;}
```

```css
a { color: pink; }
```

```css
a { color: pink;top: 0; }
```

### `"always-single-line"`

There *must always* be a single space after the semicolon in single-line declaration blocks.

The following patterns are considered violations:

```css
a { color: pink;top: 0; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; top: 0; }
```

```css
a {
  color: pink;
  top: 0;
}
```

### `"never-single-line"`

There *must never* be whitespace after the semicolon in single-line declaration blocks.

The following patterns are considered violations:

```css
a { color: pink; top: 0; }
```

The following patterns are *not* considered violations:

```css
a { color: pink;top: 0; }
```

```css
a {
  color: pink;
  top: 0;
}
```

## Further Reading

* [stylelint - declaration-block-semicolon-space-after](https://stylelint.io/user-guide/rules/declaration-block-semicolon-space-after)