Pattern: Malformed whitespace before `;` of declaration block

Issue: -

## Description

Require a single space or disallow whitespace before the semicolons of declaration blocks. This rule ignores semicolons that are preceded by Less mixins.

## Examples

### `"always"`

There *must always* be a single space before the semicolons.

The following patterns are considered violations:

```css
a { color: pink; }
```

```css
a { color: pink; top: 0; }
```

The following patterns are *not* considered violations:

```css
a { color: pink ; }
```

```css
a { color: pink ; top: 0 ; }
```

### `"never"`

There *must never* be whitespace before the semicolons.

The following patterns are considered violations:

```css
a { color: pink ; }
```

```css
a { color: pink ; top: 0 ; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a { color: pink; top: 0; }
```

### `"always-single-line"`

There *must always* be a single space before the semicolons in single-line declaration blocks.

The following patterns are considered violations:

```css
a { color: pink; }
```

The following patterns are *not* considered violations:

```css
a { color: pink ; }
```

```css
a { color: pink; top: 0; }
```

```css
a { color: pink ; top: 0 ; }
```

### `"never-single-line"`

There *must never* be whitespace before the semicolons in single-line declaration blocks.

The following patterns are considered violations:

```css
a { color: pink ; }
```

The following patterns are *not* considered violations:

```css
a { color: pink; }
```

```css
a { color: pink; top: 0; }
```

```css
a { color: pink ; top: 0 ; }
```

## Further Reading

* [stylelint - declaration-block-semicolon-space-before](https://stylelint.io/user-guide/rules/declaration-block-semicolon-space-before)