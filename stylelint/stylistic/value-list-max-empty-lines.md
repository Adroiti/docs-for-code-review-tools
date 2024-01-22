Pattern: Too many empty lines in value list

Issue: -

## Description

Limit the number of adjacent empty lines within value lists.

## Examples

`int`: Maximum number of empty lines.

For example, with `0`:

The following patterns are considered violations:

```css
a {
  padding: 10px

    10px
    10px
    10px
}
```

```css
a {
  padding: 
    10px
    10px
    10px

    10px
}
```

```css
a {
  box-shadow: inset 0 2px 0 #dcffa6,

    0 2px 5px #000;
}
```

```css
a {
  box-shadow:
    inset 0 2px 0 #dcffa6,

    0 2px 5px #000;
}
```

The following patterns are *not* considered violations:

```css
a {
  padding: 10px 10px 10px 10px
}
```

```css
a {
  padding: 10px
    10px
    10px
    10px
}
```

```css
a {
  padding:
    10px
    10px
    10px
    10px
}
```

```css
a {
  box-shadow: inset 0 2px 0 #dcffa6, 0 2px 5px #000;
}
```

```css
a {
  box-shadow: inset 0 2px 0 #dcffa6,
    0 2px 5px #000;
}
```

```css
a {
  box-shadow:
    inset 0 2px 0 #dcffa6,
    0 2px 5px #000;
}
```

## Further Reading

* [stylelint - value-list-max-empty-lines](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/value-list-max-empty-lines)