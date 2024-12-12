Pattern: Incorrect newline before value list comma

Issue: -

## Description

Require a newline or disallow whitespace before the commas of value lists.

```css
  a { background-size: 0
    , 0; }
/** ↑
 * The newline before this comma */
```

## Examples

### `"always"`

There _must always_ be a newline before the commas.

The following patterns are considered problems:

```css
a { background-size: 0,0; }
```

```css
a { background-size: 0,
      0; }
```

The following patterns are _not_ considered problems:

```css
a { background-size: 0
      , 0; }
```

### `"always-multi-line"`

There _must always_ be a newline before the commas in multi-line value lists.

The following patterns are considered problems:

```css
a { background-size: 0,
      0; }
```

The following patterns are _not_ considered problems:

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

There _must never_ be whitespace before the commas in multi-line value lists.

The following patterns are considered problems:

```css
a { background-size: 0
      , 0; }
```

The following patterns are _not_ considered problems:

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