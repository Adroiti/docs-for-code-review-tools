Pattern: Unnecessary `;`

Issue: -

## Description

Disallow extra semicolons.

```css
a { color: pink;; }
/**             ↑
 *  This semicolons */
```

This rule ignores semicolons after Less mixins.

## Examples

### `true`

The following patterns are considered problems:

```css
@import "x.css";;
```

```css
@import "x.css";
;
```

```css
a {
  color: pink;;
}
```

```css
a {
  ;color: pink;
}
```

```css
a {
  color: pink;
  ;
}
```

```css
a {
  color: red;
}
;
b {
  color: white;
}
```

The following patterns are _not_ considered problems:

```css
@import "x.css";
```

```css
a {
  color: pink;
}
```

## Further Reading

* [stylelint - no-extra-semicolons](https://stylelint.io/user-guide/rules/no-extra-semicolons)