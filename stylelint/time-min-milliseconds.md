Pattern: Time value is too low

Issue: -

## Description

This rule checks positive numbers in `transition-duration`, `transition-delay`, `animation-duration`, `animation-delay`, and those times as they manifest in the `transition` and `animation` shorthands.

## Examples

`int`: Minimum number of milliseconds for time values.

For example, with `100`:

The following patterns are considered violations:

```css
a { animation: 80ms; }
```

```css
a { transition-duration: 0.08s; }
```

```css
a { transition: background-color 6ms linear; }
```

```css
a { animation-delay: 0.01s; }
```

The following patterns are *not* considered violations:

```css
a { animation: 8s; }
```

```css
a { transition-duration: 0.8s; }
```

```css
a { transition: background-color 600ms linear; }
```

```css
a { animation-delay: 1s; }
```

## Further Reading

* [stylelint - time-min-milliseconds](https://stylelint.io/user-guide/rules/time-min-milliseconds)