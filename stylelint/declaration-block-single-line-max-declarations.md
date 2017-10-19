Pattern: Too many items in single-line declaration block

Issue: -

## Description

Limit the number of declaration within single line declaration blocks.

## Examples

`int`: Maximum number of declarations allowed.

For example, with `1`:

The following patterns are considered violations:

```css
a { color: pink; top: 3px; }
```

```css
a,
b { color: pink; top: 3px; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a,
b { color: pink; }
```

```css
a {
  color: pink;
  top: 3px;
}
```

## Further Reading

* [stylelint - declaration-block-single-line-max-declarations](https://stylelint.io/user-guide/rules/declaration-block-single-line-max-declarations)