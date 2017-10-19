Pattern: Unspaced operator in `calc()`

Issue: -

## Description

Before the operator, there must be a single whitespace or a newline plus indentation. After the operator, there must be a single whitespace or a newline.

## Examples

The following patterns are considered violations:

```css
a { top: calc(1px+2px); }
```

```css
a { top: calc(1px+ 2px); }
```

The following patterns are *not* considered violations:

```css
a { top: calc(1px + 2px); }
/**               ↑
 * The space around this operator */
```

```css
a { top: calc(calc(1em * 2) / 3); }
```

```css
a {
  top: calc(var(--foo) +
    var(--bar));
}
```

```css
a {
  top: calc(var(--foo)
    + var(--bar));
}
```

## Further Reading

* [stylelint - function-calc-no-unspaced-operator](https://stylelint.io/user-guide/rules/function-calc-no-unspaced-operator)