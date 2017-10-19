Pattern: Use of double-slash comment

Issue: -

## Description

If you are using a preprocessor that allows `//` single-line comments (e.g. Sass, Less, Stylus), this rule will not complain about those. They are compiled into standard CSS comments by your preprocessor, so stylelint will consider them valid. This rule only complains about the lesser-known method of using `//` to "comment out" a single line of code in regular CSS.

## Examples

The following patterns are considered violations:

```css
a { // color: pink; }
/** ↑
 *  This comment */
```

```css
// a { color: pink; }
```

The following patterns are *not* considered violations:

```css
a { /* color: pink; */ }
```

```css
/* a { color: pink; } */
```

## Further Reading

* [stylelint - no-invalid-double-slash-comments](https://stylelint.io/user-guide/rules/no-invalid-double-slash-comments)