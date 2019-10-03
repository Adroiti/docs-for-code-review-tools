Pattern: Unnecessary equality to `null`

Issue: -

## Description

Check for equality to null is unnecessarily explicit since `null` is falsey in Sass.

```scss
a {
    @if $x == null {}
/**         ↑     ↑
 * == or != null is unncessary */
}
```

## Examples

true

### `true`

The following patterns are considered warnings:
```scss
a {
    @if $x == null {}
}
```

```scss
a {
    @if $x != null {}
}
```

The following patterns are *not* considered warnings:

```scss
a {
    @if $x {}
}
```

```scss
a {
    @if not $x {}
}
```

## Further Reading

* [stylelint - at-if-no-null](https://github.com/kristerkari/stylelint-scss/tree/master/src/rules/at-if-no-null)