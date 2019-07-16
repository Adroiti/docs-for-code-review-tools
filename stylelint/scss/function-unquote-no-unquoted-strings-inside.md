Pattern: Unquoted string in unquote function

Issue: -

## Description

Disallow unquoted strings inside the [unquote function](https://sass-lang.com/documentation/functions/string#unquote).


## Examples

### `true`

The following patterns are considered violations:

```scss
a {
  font-family: unquote(Helvetica);
}
```

```scss
$font: Helvetica;
p {
  font-family: unquote($font);
}
```

The following patterns are _not_ considered violations:

```scss
a {
  color: unquote("blue");
}
```

```scss
$font: "Helvetica";
p {
  font-family: unquote($font);
}
```

## Further Reading

* [stylelint - function-unquote-no-unquoted-strings-inside](https://stylelint.io/user-guide/rules/function-unquote-no-unquoted-strings-inside)