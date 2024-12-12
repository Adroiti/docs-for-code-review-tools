Pattern: Incorrect spacing after opening brace

Issue: -

## Description

Require a single space or disallow whitespace after the opening brace of blocks.

```css
  a { color: pink; }
/** ↑
 * The space after this brace */
```

## Examples

`string`: `"always"|"never"|"always-single-line"|"never-single-line"|"always-multi-line"|"never-multi-line"`

### `"always"`

There _must always_ be a single space after the opening brace.

The following patterns are considered problems:

```css
a {color: pink; }
```

```css
a {
color: pink; }
```

The following patterns are _not_ considered problems:

```css
a { color: pink; }
```

```css
a { color: pink;
}
```

### `"never"`

There _must never_ be whitespace after the opening brace.

The following patterns are considered problems:

```css
a { color: pink; }
```

```css
a {
color: pink; }
```

The following patterns are _not_ considered problems:

```css
a {color: pink; }
```

```css
a
{color: pink; }
```

### `"always-single-line"`

There _must always_ be a single space after the opening brace in single-line blocks.

The following patterns are considered problems:

```css
a {color: pink; }
```

The following patterns are _not_ considered problems:

```css
a { color: pink; }
```

```css
a {color: pink;
}
```

### `"never-single-line"`

There _must never_ be whitespace after the opening brace in single-line blocks.

The following patterns are considered problems:

```css
a { color: pink; }
```

The following patterns are _not_ considered problems:

```css
a {color: pink; }
```

```css
a { color: pink;
}
```

### `"always-multi-line"`

There _must always_ be a single space after the opening brace in multi-line blocks.

The following patterns are considered problems:

```css
a {color: pink;
}
```

The following patterns are _not_ considered problems:

```css
a {color: pink; }
```

```css
a { color: pink;
}
```

### `"never-multi-line"`

There _must never_ be whitespace after the opening brace in multi-line blocks.

The following patterns are considered problems:

```css
a { color: pink;
}
```

The following patterns are _not_ considered problems:

```css
a { color: pink; }
```

```css
a {color: pink;
}
```

## Configuration

### `ignore: ["at-rules"]`

Ignore the opening brace of at-rules.

For example, with `"always"`:

The following pattern is _not_ considered a problem:

```css
@media print {
  a { color: pink; }
}
```

## Further Reading

* [stylelint - block-opening-brace-space-after](https://stylelint.io/user-guide/rules/block-opening-brace-space-after)