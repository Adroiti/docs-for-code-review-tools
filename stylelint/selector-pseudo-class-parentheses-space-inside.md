Pattern: Malformed whitespace for parentheses in pseudo-class selector

Issue: -

## Description

Require a single space or disallow whitespace on the inside of the parentheses within pseudo-class selectors.

## Examples

### `"always"`

There *must always* be a single space inside the parentheses.

The following patterns are considered violations:

```css
input:not([type="submit"]) {}
```

```css
input:not([type="submit"] ) {}
```

The following patterns are *not* considered violations:

```css
input:not( [type="submit"] ) {}
```

### `"never"`

There *must never* be whitespace on the inside the parentheses.

The following patterns are considered violations:

```css
input:not( [type="submit"] ) {}
```

```css
input:not( [type="submit"]) {}
```

The following patterns are *not* considered violations:

```css
input:not([type="submit"]) {}
```

## Further Reading

* [stylelint - selector-pseudo-class-parentheses-space-inside](https://stylelint.io/user-guide/rules/selector-pseudo-class-parentheses-space-inside)