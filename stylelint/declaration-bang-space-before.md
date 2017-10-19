Pattern: Malformed whitespace before `!` of declaration

Issue: -

## Description

Require a single space or disallow whitespace before the bang of declarations.

## Examples

### `"always"`

There *must always* be a single space before the bang.

The following patterns are considered violations:

```css
a { color: pink!important; }
```

```css
a { color: pink  ! important; }
```

The following patterns are *not* considered violations:

```css
a { color: pink !important; }
```

```css
a { color:pink ! important; }
```

### `"never"`

There *must never* be whitespace before the bang.

The following patterns are considered violations:

```css
a { color : pink !important; }
```

The following patterns are *not* considered violations:

```css
a { color: pink!important; }
```

```css
a { color: pink! important; }
```

## Further Reading

* [stylelint - declaration-bang-space-before](https://stylelint.io/user-guide/rules/declaration-bang-space-before)