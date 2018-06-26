Pattern: Duplicate `$`-variable

Issue: -

## Description

Disallow duplicate dollar variables within a stylesheet.

```scss
    $a: 1;
    $a: 2;
/** ↑
 * These are duplicates */
```

## Examples

### `true`

The following patterns are considered violations:

```scss
$a: 1;
$a: 2;
```

```scss
$a: 1;
$b: 2;
$a: 3;
```

```scss
$a: 1;
.b {
  $a: 1;
}
```

The following patterns are *not* considered violations:

```scss
$a: 1;
$b: 2;
```

```scss
$a: 1;
.b {
  $b: 2;
}
```

## Further Reading

* [stylelint-scss - no-duplicate-dollar-variables](https://github.com/kristerkari/stylelint-scss/tree/master/src/rules/no-duplicate-dollar-variables)