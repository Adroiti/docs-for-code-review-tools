Pattern: Use of empty comment

Issue: -

## Description

Disallow empty comments.

## Examples

### `true`

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
/**/
```

<!-- prettier-ignore -->
```css
/* */
```

<!-- prettier-ignore -->
```css
/*

 */
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
/* comment */
```

<!-- prettier-ignore -->
```css
/*
 * Multi-line Comment
**/
```

## Further Reading

* [stylelint - comment-no-empty](https://stylelint.io/user-guide/rules/comment-no-empty)