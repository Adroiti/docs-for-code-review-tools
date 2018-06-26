Pattern: Malformed space before `@mixin` parentheses

Issue: -

## Description

Require or disallow a space before `@mixin` parentheses.

```scss
@mixin foo ($arg) { }
/**        ↑
 * The space before this parenthesis */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There *must always* be exactly one space between the mixin name and the opening parenthesis. 

*Note: This rule does not enforce parentheses to be present in a declaration without arguments.*

The following patterns are considered warnings:

```scss
@mixin foo($arg) { }
```
```scss
@mixin foo  ($arg) { }
```

The following patterns are *not* considered warnings:

```scss
@mixin foo ($arg) { }
```
```scss
@mixin foo { }
```

### `"never"`

There *must never* be any whitespace between the mixin name and the opening parenthesis.

The following patterns are considered warnings:

```scss
@mixin foo ($arg) { }
```

The following patterns are *not* considered warnings:

```scss
@mixin foo($arg) { }
```
```scss
@mixin foo { }
```

## Further Reading

* [stylelint-scss - at-mixin-parentheses-space-before](https://github.com/kristerkari/stylelint-scss/blob/master/src/rules/at-mixin-parentheses-space-before)