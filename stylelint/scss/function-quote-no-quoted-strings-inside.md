Pattern: Quoted string in quote function

Issue: -

## Description

Disallow quoted strings inside the [quote function](https://sass-lang.com/documentation/functions/string#quote).

## Examples

### `true`

The following patterns are considered violations:

```scss
a {
  font-family: quote("Helvetica");
}
```

```scss
$font: "Helvetica";
p {
  font-family: quote($font);
}
```

The following patterns are _not_ considered violations:

```scss
a {
  color: quote(blue);
}
```

```scss
$font: Helvetica;
p {
  font-family: quote($font);
}
```

## Further Reading

* [stylelint - function-quote-no-quoted-strings-inside](https://stylelint.io/user-guide/rules/function-quote-no-quoted-strings-inside)