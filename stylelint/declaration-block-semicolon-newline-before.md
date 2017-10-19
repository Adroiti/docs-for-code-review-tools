Pattern: Malformed newline before `;` of declaration block

Issue: -

## Description

Require a newline or disallow whitespace before the semicolons of declaration blocks. This rule ignores semicolons that are preceded by Less mixins.

## Examples

### `"always"`

There *must always* be a newline before the semicolons.

The following patterns are considered violations:

```css
a { color: pink; }
```

```css
a {
  color: pink; top: 0;
}
```

The following patterns are *not* considered violations:

```css
a { color: pink
; }
```

```css
a {
  color: pink
  ; top: 0;
}
```

### `"always-multi-line"`

There *must always* be a newline before the semicolons in multi-line rules.

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
  color: pink
  ; top: 0;
}
```

### `"never-multi-line"`

There *must never* be whitespace before the semicolons in multi-line rules.

The following patterns are considered violations:

```css
a {
  color: pink
  ; top: 0;
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

## Further Reading

* [stylelint - declaration-block-semicolon-newline-before](https://stylelint.io/user-guide/rules/declaration-block-semicolon-newline-before)