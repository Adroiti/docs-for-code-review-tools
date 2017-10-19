Pattern: Malformed whitespace in `[]` for attribute selector

Issue: -

## Description

Require a single space or disallow whitespace on the inside of the brackets within attribute selectors.

## Examples

### `"always"`

There *must always* be a single space inside the brackets.

The following patterns are considered violations:

```css
[target] {}
```

```css
[ target] {}
```

```css
[target ] {}
```

```css
[target=_blank] {}
```

```css
[ target=_blank] {}
```

```css
[target=_blank ] {}
```

The following patterns are *not* considered violations:

```css
[ target ] {}
```

```css
[ target=_blank ] {}
```

### `"never"`

There *must never* be whitespace on the inside the brackets.

The following patterns are considered violations:

```css
[ target] {}
```

```css
[target ] {}
```

```css
[ target ] {}
```

```css
[ target=_blank] {}
```

```css
[target=_blank ] {}
```

```css
[ target=_blank ] {}
```

The following patterns are *not* considered violations:

```css
[target] {}
```

```css
[target=_blank] {}
```

## Further Reading

* [stylelint - selector-attribute-brackets-space-inside](https://stylelint.io/user-guide/rules/selector-attribute-brackets-space-inside)