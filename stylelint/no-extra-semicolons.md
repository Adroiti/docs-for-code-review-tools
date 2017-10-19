Pattern: Extra `;`

Issue: -

## Description

Disallow extra semicolons. This rule ignores semicolons after Less mixins.

## Examples

The following patterns are considered violations:

```css
a { color: pink;; }
/**             ↑
 *  This semicolon */
```

```css
@import "x.css";;
```

```css
@import "x.css";
;
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

The following patterns are *not* considered violations:

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