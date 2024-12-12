Pattern: Missing newline after opening brace

Issue: -

## Description

Require a newline after the opening brace of blocks.

```css
  a {
    ↑ color: pink; }
/** ↑
 * The newline after this brace */
```

This rule allows an end-of-line comment followed by a newline. For example,

```css
a { /* end-of-line comment */
  color: pink;
}
```

## Examples

### `"always"`

There _must always_ be a newline after the opening brace.

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

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

There _must always_ be a newline after the opening brace in multi-line blocks.

The following patterns are considered problems:

```css
a{color: pink;
}
```

The following patterns are _not_ considered problems:

```css
a { color: pink; }
```

```css
a {
color: pink; }
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

### `ignore: ["rules"]`

Ignore the opening brace of rules.

For example, with `"always"`:

The following pattern is _not_ considered a problem:

```css
a { color: pink; }
```

## Further Reading

* [stylelint - block-opening-brace-newline-after](https://stylelint.io/user-guide/rules/block-opening-brace-newline-after)