Pattern: Malformed whitespace before `,` in value list

Issue: -

## Description

Require a single space or disallow whitespace before the commas of value lists.

## Examples

### `"always"`

There *must always* be a single space before the commas.

The following patterns are considered violations:

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0
      , 0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0 ,0; }
```

```css
a { background-size: 0 ,
      0; }
```

### `"never"`

There *must never* be whitespace before the commas.

The following patterns are considered violations:

```css
a { background-size: 0 ,0; }
```

```css
a { background-size: 0 ,
      0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0,
      0; }
```

### `"always-single-line"`

There *must always* be a single space before the commas in single-line value lists.

The following patterns are considered violations:

```css
a { background-size: 0,0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0 ,0; }
```

```css
a { background-size: 0 ,
      0; }
```

```css
a { background-size: 0
      , 0; }
```

### `"never-single-line"`

There *must never* be whitespace before the commas in single-line value lists.

The following patterns are considered violations:

```css
a { background-size: 0 ,0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0,
      0; }
```

```css
a { background-size: 0 ,
      0; }
```

## Further Reading

* [stylelint - value-list-comma-space-before](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/value-list-comma-space-before)