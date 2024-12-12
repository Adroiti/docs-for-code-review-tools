Pattern: Incorrect spacing inside attribute selector brackets

Issue: -

## Description

Require a single space or disallow whitespace on the inside of the brackets within attribute selectors.

```css
    [ target=_blank ]
/** ↑               ↑
 * The space inside these two brackets */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space inside the brackets.

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

```css
[ target ] {}
```

```css
[ target=_blank ] {}
```

### `"never"`

There _must never_ be whitespace on the inside the brackets.

The following patterns are considered problems:

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

The following patterns are _not_ considered problems:

```css
[target] {}
```

```css
[target=_blank] {}
```

## Further Reading

* [stylelint - selector-attribute-brackets-space-inside](https://stylelint.io/user-guide/rules/selector-attribute-brackets-space-inside)