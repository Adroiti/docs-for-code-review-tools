Pattern: Malformed unit case

Issue: -

## Description

Specify lowercase or uppercase for units.

```css
    a { width: 10px; }
/**              ↑
 *     These units */
```

## Examples

`string`: `"lower"|"upper"`

### `"lower"`

The following patterns are considered problems:

```css
a {
  width: 10PX;
}
```

```css
a {
  width: 10Px;
}
```

```css
a {
  width: 10pX;
}
```

```css
a {
  width: 10PIXEL;
}
```

```css
a {
  width: calc(10PX * 2);
}
```

The following patterns are _not_ considered problems:

```css
a {
  width: 10px;
}
```

```css
a {
  width: calc(10px * 2);
}
```

### `"upper"`

The following patterns are considered problems:

```css
a {
  width: 10px;
}
```

```css
a {
  width: 10Px;
}
```

```css
a {
  width: 10pX;
}
```

```css
a {
  width: 10pixel;
}
```

```css
a {
  width: calc(10px * 2);
}
```

The following patterns are _not_ considered problems:

```css
a {
  width: 10PX;
}
```

```css
a {
  width: calc(10PX * 2);
}
```

## Further Reading

* [stylelint - unit-case](https://stylelint.io/user-guide/rules/unit-case)