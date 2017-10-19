Pattern: Inconsistent function name case 

Issue: -

## Description

Specify lowercase or uppercase for function names. Camel case function names, e.g. `translateX`, are accounted for when the `lower` option is used.

## Examples

### `"lower"`

The following patterns are considered violations:

```css
a {
  width: Calc(5% - 10em);
}
```

```css
a {
  width: cAlC(5% - 10em);
}
```

```css
a {
  width: CALC(5% - 10em);
}
```

```css
a {
  background: -WEBKIT-RADIAL-GRADIENT(red, green, blue);
}
```

The following patterns are *not* considered violations:

```css
a {
  width: calc(5% - 10em);
}
```

```css
a {
  background: -webkit-radial-gradient(red, green, blue);
}
```

### `"upper"`

The following patterns are considered violations:

```css
a {
  width: Calc(5% - 10em);
}
```

```css
a {
  width: cAlC(5% - 10em);
}
```

```css
a {
  width: calc(5% - 10em);
}
```

```css
a {
  background: -webkit-radial-gradient(red, green, blue);
}
```

The following patterns are *not* considered violations:

```css
a {
  width: CALC(5% - 10em);
}
```

```css
a {
  background: -WEBKIT-RADIAL-GRADIENT(red, green, blue);
}
```

# Configuration

### `ignoreFunctions: ["/regex/", "non-regex"]`

Ignore case of function names.

For example, with `"lower"`.

Given:

```js
["some-function", "/^get.*$/"]
```

The following patterns are considered violations:

```css
a {
  color: sOmE-FuNcTiOn();
}
```

```css
a {
  color: some-other-function();
}
```

```css
a {
  color: GetColor();
}
```

```css
a {
  color: GET_COLOR();
}
```

The following patterns are *not* considered violations:

```css
a {
  display: some-function();
}
```


```css
a {
  display: getColor();
}
```

```css
a {
  display: get_color();
}
```

## Further Reading

* [stylelint - function-name-case](https://stylelint.io/user-guide/rules/function-name-case)