Pattern: Use of `/*`-comment

Issue: -

## Description

Disallow `/*`-comments. This rule only works on CSS comments (`/* */`) and ignores all double-slash (`//`) comments.

## Examples

### `true`

The following patterns are considered violations:

```scss
/* comment */
```

```scss
/*
 * comment
*/
```

The following patterns are *not* considered warnings:

```scss
// comment
```

## Further Reading

* [stylelint - comment-no-loud](https://stylelint.io/user-guide/rules/comment-no-loud)