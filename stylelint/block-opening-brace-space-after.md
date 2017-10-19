Pattern: Malformed whitespace after `{` of block

Issue: -

## Description

Require a single space or disallow whitespace after the opening brace of blocks.

## Examples

### `"always"`

There *must always* be a single space after the opening brace.

The following patterns are considered violations:

```css
a {color: pink; }
```

```css
a {
color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a { color: pink;
}
```

### `"never"`

There *must never* be whitespace after the opening brace.

The following patterns are considered violations:

```css
a { color: pink; }
```

```css
a {
color: pink; }
```

The following patterns are *not* considered violations:

```css
a {color: pink; }
```

```css
a
{color: pink; }
```

### `"always-single-line"`

There *must always* be a single space after the opening brace in single-line blocks.

The following patterns are considered violations:

```css
a {color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a {color: pink;
}
```

### `"never-single-line"`

There *must never* be whitespace after the opening brace in single-line blocks.

The following patterns are considered violations:

```css
a { color: pink; }
```

The following patterns are *not* considered violations:

```css
a {color: pink; }
```

```css
a { color: pink;
}
```

### `"always-multi-line"`

There *must always* be a single space after the opening brace in multi-line blocks.

The following patterns are considered violations:

```css
a {color: pink;
}
```

The following patterns are *not* considered violations:

```css
a {color: pink; }
```

```css
a { color: pink;
}
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

* [stylelint - block-opening-brace-space-after](https://stylelint.io/user-guide/rules/block-opening-brace-space-after)