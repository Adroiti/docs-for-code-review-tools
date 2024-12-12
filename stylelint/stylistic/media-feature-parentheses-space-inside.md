Pattern: Incorrect spacing inside media feature parentheses

Issue: -

## Description

Require a single space or disallow whitespace on the inside of the parentheses within media features.

```css
@media ( max-width: 300px ) {}
/**    ↑                  ↑
 * The space inside these two parentheses */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There _must always_ be a single space inside the parentheses.

The following patterns are considered problems:

```css
@media (max-width: 300px) {}
```

```css
@media (max-width: 300px ) {}
```

The following patterns are _not_ considered problems:

```css
@media ( max-width: 300px ) {}
```

### `"never"`

There _must never_ be whitespace on the inside the parentheses.

The following patterns are considered problems:

```css
@media ( max-width: 300px ) {}
```

```css
@media ( max-width: 300px) {}
```

The following patterns are _not_ considered problems:

```css
@media (max-width: 300px) {}
```

## Further Reading

* [stylelint - media-feature-parentheses-space-inside](https://stylelint.io/user-guide/rules/media-feature-parentheses-space-inside)