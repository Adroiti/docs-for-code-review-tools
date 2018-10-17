Pattern: Use of `$`-variable

Issue: -

## Description

Disallow dollar variables within a stylesheet.

```scss
    $a: 1;
/** ↑
 * These dollar variables */
```

## Examples

### `true`

The following patterns are considered violations:

```scss
$a: 1;
```

```scss
$a: 1;
$b: 2;
```

```scss
.b {
  $a: 1;
}
```

The following patterns are *not* considered violations:

```scss
a {
  color: blue;
}
```

## Further Reading

* [stylelint-scss - no-duplicate-dollar-variables](https://github.com/kristerkari/stylelint-scss/tree/master/src/rules/no-duplicate-dollar-variables)