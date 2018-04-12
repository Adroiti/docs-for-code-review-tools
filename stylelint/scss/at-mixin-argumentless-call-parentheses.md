Pattern: Malformed parentheses for argumentless `@mixin` call

Issue: -

## Description

Require or disallow parentheses in argumentless `@mixin` calls.

```scss
@include mixin-name() {
/**                ↑
 *                 Such mixin calls */
```

## Examples

`string`: `"always"|"never"`

### `"always"`

There *must always* be parentheses in mixin calls, even if no arguments are passed.

The following patterns are considered warnings:

```scss
@include mixin-name;
```

The following patterns are *not* considered warnings:

```scss
@include mixin-name();
```

### `"never"`

There *must never* be parentheses when calling a mixin without arguments.

The following patterns are considered warnings:

```scss
@include mixin-name();
```

The following patterns are *not* considered warnings:

```scss
@include mixin-name;
```

## Further Reading

* [stylelint-scss - at-mixin-argumentless-call-parentheses](https://github.com/kristerkari/stylelint-scss/blob/master/src/rules/at-mixin-argumentless-call-parentheses/README.md)