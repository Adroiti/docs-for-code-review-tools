Pattern: Missing pattern for `%`-placeholder

Issue: -

## Description

Specify a pattern for `%`-placeholders.

```scss
    %foobar { display: flex; }
/** ↑
 * The pattern of this */
```

## Examples

`regex` or `string`

A string will be translated into a RegExp like so `new RegExp(yourString)` — so be sure to escape properly.

Nested selectors will be resolved before checking.

The selector value *after `%`* will be checked. No need to include `%` in your pattern.

### E.g. `/^foo-[a-z]+$/`

The following patterns are considered warnings:

```scss
%myriad { display: flex; }
```

```scss
%foo-bar { 
  &-supa { display: flex; } /* %foo-bar matches, but %foo-bar-supa doesn't */
}
```

```scss
%foo- { /* %foo- on the 1st leves doesn't match */
  &bar { display: flex; }
}
```

The following patterns are *not* considered warnings:

```scss
%foo-aimp { display: flex; }
```

```scss
%foo-bar { 
  &lignt { display: flex; }
}
```

```scss
.p {
  @extend %mathy; // The rule only checks placeholder definitions
}
```

## Further Reading

* [stylelint-scss - percent-placeholder-pattern](https://github.com/kristerkari/stylelint-scss/blob/master/src/rules/percent-placeholder-pattern/README.md)