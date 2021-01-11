Pattern: Invalid comment pattern

Issue: -

## Description

Specify a pattern for comments.

```css
/*  comment */
/** ↑
 * The pattern of this */
```

## Examples

The following patterns are considered violations:

```css
/*not starting with foo*/
a { color: red; }
```

The following patterns are _not_ considered violations:

```css
/*foo at the beginning*/
a { color: red; }
```

## Further Reading

* [stylelint - comment-pattern](https://stylelint.io/user-guide/rules/comment-pattern)