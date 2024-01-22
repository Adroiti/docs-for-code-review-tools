Pattern: Malformed whitespace before `:` of declaration

Issue: -

## Description

Require a single space or disallow whitespace before the colon of declarations.

## Examples

### `"always"`

There *must always* be a single space before the colon.

The following patterns are considered violations:

```css
a { color: pink }
```

```css
a { color:pink }
```

The following patterns are *not* considered violations:

```css
a { color : pink }
```

```css
a { color :pink }
```

### `"never"`

There *must never* be whitespace before the colon.

The following patterns are considered violations:

```css
a { color : pink }
```

```css
a { color :pink }
```

The following patterns are *not* considered violations:

```css
a { color: pink }
```

```css
a { color:pink }
```

## Further Reading

* [stylelint - declaration-colon-space-before](https://github.com/stylelint-stylistic/stylelint-stylistic/tree/main/lib/rules/declaration-colon-space-before)