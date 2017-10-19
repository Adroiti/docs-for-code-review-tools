Pattern: Malformed whitespace after `,` in value list

Issue: -

## Description

Require a single space or disallow whitespace after the commas of value lists.

## Examples

### `"always"`

There *must always* be a single space after the commas.

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
a { background-size: 0, 0; }
```

```css
a { background-size: 0
      , 0; }
```

### `"never"`

There *must never* be whitespace after the commas.

The following patterns are considered violations:

```css
a { background-size: 0, 0; }
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
a { background-size: 0
      ,0; }
```

### `"always-single-line"`

There *must always* be a single space after the commas in single-line value lists.

The following patterns are considered violations:

```css
a { background-size: 0,0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0, 0; }
```

```css
a { background-size: 0
    , 0; }
```

```css
a { background-size: 0
      ,0; }
```

### `"never-single-line"`

There *must never* be whitespace after the commas in single-line value lists.

The following patterns are considered violations:

```css
a { background-size: 0, 0; }
```

The following patterns are *not* considered violations:

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0
      ,0; }
```

```css
a { background-size: 0
      , 0; }
```

## Further Reading

* [stylelint - value-list-comma-space-after](https://stylelint.io/user-guide/rules/value-list-comma-space-after)