Pattern: Duplicate mixin

Issue: -

## Description

Disallow duplicate mixins within a stylesheet.

```scss
@mixin font-size-default {
  font-size: 16px;
}
@mixin font-size-default {
  font-size: 18px;
}
/** ↑
 * These are duplicates */
```

## Examples

### `true`

The following patterns are considered violations:

```scss
@mixin font-size-default {
  font-size: 16px;
}
@mixin font-size-default {
  font-size: 18px;
}
```

```scss
@mixin font-size-default {
  font-size: 16px;
}
@mixin font-size-sm {
  font-size: 14px;
}
@mixin font-size-default {
  font-size: 18px;
}
```

```scss
@mixin font-size {
  font-size: 16px;
}
@mixin font-size($var) {
  font-size: $var;
}
```

```scss
@mixin font-size($property, $value) {
  #{$property}: $value;
}
@mixin font-size($var) {
  font-size: $var;
}
```

```scss
@mixin font-size {
  color: blue;
}

.b {
  @mixin font-size {
    color: red;
  }
  @include font-size;
}
```

The following patterns are _not_ considered violations:

```scss
@mixin font-size-default {
  font-size: 16px;
}
@mixin font-size-lg {
  font-size: 18px;
}
```

## Further Reading

* [stylelint-scss - no-duplicate-mixins](https://github.com/kristerkari/stylelint-scss/tree/master/src/rules/no-duplicate-mixins)