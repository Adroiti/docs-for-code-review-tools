Pattern: Malformed newline before `,` in value list

Issue: -

## Description

Require a newline or disallow whitespace before the commas of value lists.

## Examples

### `"always"`

There *must always* be a newline before the commas.

The following patterns are considered violations:

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0,
      0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0
      , 0; }
```

### `"always-multi-line"`

There *must always* be a newline before the commas in multi-line value lists.

The following patterns are considered violations:

```css
a { background-size: 0,
      0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0, 0; }
```

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0
      , 0; }
```

### `"never-multi-line"`

There *must never* be whitespace before the commas in multi-line value lists.

The following patterns are considered violations:

```css
a { background-size: 0
      , 0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0, 0; }
```

```css
a { background-size: 0,
      0; }
```

## Further Reading

* [stylelint - value-list-comma-newline-before](https://stylelint.io/user-guide/rules/value-list-comma-newline-before)