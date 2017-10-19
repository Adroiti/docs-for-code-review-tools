Pattern: Too many empty lines in selector

Issue: -

## Description

Limit the number of adjacent empty lines within selectors.

## Examples

`int`: Maximum number of empty lines.

For example, with `0`:

The following patterns are considered violations:

```css
a

b {
  color: red;
}
```

```css
a,

b {
  color: red;
}
```

```css
a

>
b {
  color: red;
}
```

```css
a
>

b {
  color: red;
}
```

The following patterns are *not* considered violations:

```css
a b {
  color: red;
}
```

```css
a
b {
  color: red;
}
```

```css
a,
b {
  color: red;
}
```

```css
a > b {
  color: red;
}
```

```css
a
>
b {
  color: red;
}
```

## Further Reading

* [stylelint - selector-max-empty-lines](https://stylelint.io/user-guide/rules/selector-max-empty-lines)