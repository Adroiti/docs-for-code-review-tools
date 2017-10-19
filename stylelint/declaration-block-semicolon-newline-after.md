Pattern: Malformed newline after `;` of declaration block

Issue: -

## Description

Require a newline or disallow whitespace after the semicolons of declaration blocks. 

This rule ignores semicolons that are preceded by Less mixins. 

This rule ignores the last semicolon of declaration blocks. Use the `block-closing-brace-*-before` rules to control the whitespace between the last semicolon and the closing brace instead.

This rule allows an end-of-line comment followed by a newline. For example:

```css
a {
  color: pink; /* end-of-line comment */
  top: 0;
}
```

## Examples

### `"always"`

There *must always* be a newline after the semicolon.

The following patterns are considered violations:

```css
a { color: pink; top: 0; }
```

```css
a {
  color: pink; /* end-of-line comment
    containing a newline */
  top: 0;
}
```

The following patterns are *not* considered violations:

```css
a {
  color: pink;
  top: 0;
}
```

```css
a {
  color: pink; /* end-of-line comment */
  top: 0;
}
```

### `"always-multi-line"`

There *must always* be a newline after the semicolon in multi-line rules.

The following patterns are considered violations:

```css
a {
  color: pink; top: 0;
}
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a { color: pink; top: 0; }
```

```css
a {
  color: pink;
  top: 0;
}
```

### `"never-multi-line"`

There *must never* be whitespace after the semicolon in multi-line rules.

The following patterns are considered violations:

```css
a {
  color: pink;
  top: 0;
}
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a { color: pink; top: 0; }
```

```css
a {
  color: pink
  ; top: 0;
}
```

## Further Reading

* [stylelint - declaration-block-semicolon-newline-after](https://stylelint.io/user-guide/rules/declaration-block-semicolon-newline-after)