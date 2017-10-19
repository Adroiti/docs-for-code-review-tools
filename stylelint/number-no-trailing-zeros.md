Pattern: Trailing zeros in number

Issue: -

## Description

Disallow trailing zeros in numbers.

## Examples

The following patterns are considered violations:

```css
a { top: 0.5000px; bottom: 1.0px; }
/**         ↑                ↑
 *        These trailing zeros */
```

```css
a { top: 1.01000px }
```

The following patterns are *not* considered violations:

```css
a { top: 1px }
```

```css
a { top: 1.01px }
```

## Further Reading

* [stylelint - number-no-trailing-zeros](https://stylelint.io/user-guide/rules/number-no-trailing-zeros)