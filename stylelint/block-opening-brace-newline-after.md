Pattern: Missing newline after `{` of block

Issue: -

## Description

Require a newline after the opening brace of blocks. This rule allows an end-of-line comment followed by a newline. For example:

```css
a { /* end-of-line comment */
  color: pink;
}
```

## Examples

### `"always"`

There *must always* be a newline after the opening brace.

The following patterns are considered violations:

```css
a{ color: pink; }
```

```css
a{ color: pink;
}
```

```css
a{ /* end-of-line comment
  with a newline */
  color: pink;
}
```

The following patterns are *not* considered violations:

```css
a {
color: pink; }
```

```css
a
{
color: pink; }
```

```css
a { /* end-of-line comment */
  color: pink;
}
```

### `"always-multi-line"`

There *must always* be a newline after the opening brace in multi-line blocks.

The following patterns are considered violations:

```css
a{color: pink;
}
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a {
color: pink; }
```

### `"never-multi-line"`

There *must never* be whitespace after the opening brace in multi-line blocks.

The following patterns are considered violations:

```css
a { color: pink;
}
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a {color: pink;
}
```

## Further Reading

* [stylelint - block-opening-brace-newline-after](https://stylelint.io/user-guide/rules/block-opening-brace-newline-after)