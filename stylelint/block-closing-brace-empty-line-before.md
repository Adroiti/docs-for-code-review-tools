Pattern: Malformed empty line before `}` of block

Issue: -

## Description

Require or disallow an empty line before the closing brace of blocks.

## Examples

### `always-multi-line`

The following patterns are considered violations:

```css
a {
  color: pink;
}
```

The following patterns are *not* considered violations:

```css
a {
  color: pink;

}
```

```css
a { color: pink; }
```

### `never`

The following patterns are considered violations:

```css
a {
  color: pink;

}
```

The following patterns are *not* considered violations:

```css
a {
  color: pink;
}
```

```css
a { color: pink; }
```

## Further Reading

* [stylelint - block-closing-brace-empty-line-before](https://stylelint.io/user-guide/rules/block-closing-brace-empty-line-before)