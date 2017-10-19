Pattern: Malformed font-weight value

Issue: -

## Description

Require numeric or named (where possible) font-weight values. Valid font-weight names are `normal`, `bold`, `bolder`, and `lighter`. 

This rule ignores `$sass`, `@less`, and `var(--custom-property)` variable syntaxes.

## Examples

### `"numeric"`

`font-weight` values *must always* be numbers.

The following patterns are considered violations:

```css
a { font-weight: bold; }
```

```css
a { font: italic normal 20px; }
```

The following patterns are *not* considered violations:

```css
a { font-weight: 700; }
```

```css
a { font: italic 900 20px; }
```

### `"named-where-possible"`

`font-weight` values *must always* be keywords when an appropriate keyword is available.

This means that only `400` and `700` will be rejected, because those are the only numbers with keyword equivalents (`normal` and `bold`).

The following patterns are considered violations:

```css
a { font-weight: 700; }
```

```css
a { font: italic 400 20px; }
```

The following patterns are *not* considered violations:

```css
a { font-weight: bold; }
```

```css
a { font: italic normal 20px; }
```

# Configuration

### `ignore: ["relative"]`

Ignore the [*relative*](https://drafts.csswg.org/css-fonts/#font-weight-prop) keyword names of `bolder` and `lighter`.

The following patterns are *not* considered violations:

```css
a { font-weight: 400; }
a b { font-weight: lighter; }
```

## Further Reading

* [stylelint - font-weight-notation](https://stylelint.io/user-guide/rules/font-weight-notation)