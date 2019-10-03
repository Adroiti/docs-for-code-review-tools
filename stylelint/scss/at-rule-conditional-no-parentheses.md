Pattern: Unexpected `()` used to surround `@`-rule

Issue: -

## Description

Disallows parentheses in conditional `@` rules (`if`, `elsif`, `while`)

```css
    @if (true) {}
/**     ↑    ↑
 * Get rid of parentheses like this. */
```



## Examples

### `true`

The following patterns are considered warnings:

```scss
@if(true)
```

```scss
@else if(true)
```

```scss
@while(true)
```

The following patterns are *not* considered warnings:

```scss
@if true
```

```scss
@else if true
```

```scss
@while true
```

## Further Reading

* [stylelint - at-rule-conditional-no-parentheses](https://github.com/kristerkari/stylelint-scss/tree/master/src/rules/at-rule-conditional-no-parentheses)