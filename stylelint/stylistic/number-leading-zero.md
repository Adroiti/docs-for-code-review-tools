Pattern: Malformed leading zero for fractional number

Issue: -

## Description

Require or disallow a leading zero for fractional numbers less than 1.

## Examples

### `"always"`

There *must always* be a leading zero.

The following patterns are considered violations:

```css
a { line-height: .5; }
```

```css
a { transform: translate(2px, .4px); }
```

The following patterns are *not* considered violations:

```css
a { line-height: 0.5; }
```

```css
a { transform: translate(2px, 0.4px); }
```

### `"never"`

There *must never* be a leading zero.

The following patterns are considered violations:

```css
a { line-height: 0.5; }
```

```css
a { transform: translate(2px, 0.4px); }
```

The following patterns are *not* considered violations:

```css
a { line-height: .5; }
```

```css
a { transform: translate(2px, .4px); }
```

## Further Reading

* [stylelint - number-leading-zero](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/number-leading-zero)