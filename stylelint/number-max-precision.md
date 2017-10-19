Pattern: Too many decimal places in number

Issue: -

## Description

Limit the number of decimal places allowed in numbers.

## Examples

`int`: Maximum number of decimal places allowed.

For example, with `2`:

The following patterns are considered violations:

```css
a { top: 3.245px; }
```

```css
a { top: 3.245634px; }
```

```css
@media (min-width: 3.234em) {}
```

The following patterns are *not* considered violations:

```css
a { top: 3.24px; }
```

```css
@media (min-width: 3.23em) {}
```

# Configuration

### `ignoreUnits: ["/regex/", "string"]`

Ignore the precision of numbers for values with the specified units.

For example, with `2`.

Given:

```js
["/^some-/", "%"]
```

The following patterns are considered violations:

```css
a { top: 3.245px; }
```

```css
a { top: 3.245634px; }
```

```css
@media (min-width: 3.234em) {}
```

The following patterns are *not* considered violations:

```css
a { top: 3.245%; }
```

```css
@media (min-width: 3.23em) {}
```

```css
a {
  width: 10.5432%;
}
```

```css
a { top: 3.245some-unit; }
```

```css
a {
  width: 10.989some-other-unit;
}
```

## Further Reading

* [stylelint - number-max-precision](https://stylelint.io/user-guide/rules/number-max-precision)