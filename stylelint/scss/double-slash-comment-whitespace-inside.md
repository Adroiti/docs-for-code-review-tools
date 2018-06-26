Pattern: Malformed whitespace in `//`-comment

Issue: -

## Description

Require or disallow whitespace after the `//` in `//`-comments

```scss
a {
  width: 10px; // inline-comment
/*               ↑
 * Such whitespace */
```

This rule only works with SCSS-like [single-line comments](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#comments) and ignores CSS comments (`/* */`).

Any number of slashes are allowed at the beginning of the comment. So `/// comment` is treated the same way as `// comment`.

Note that a newline is not possible as a whitespace in terms of this rule as `//`-comments are intended to be single-line.

## Examples

`string`: `"always"|"never"`

### `"always"`

There *must always* be whitespace after the `//` inside `//`-comments.

The following patterns are considered warnings:

```scss
//comment
```

The following patterns are *not* considered warnings:

```scss
// comment
```

```scss
///   comment
```

### `"never"`

There *must never* be whitespace after the `//` inside `//`-comments.

The following patterns are considered warnings:

```scss
// comment
```

The following patterns are *not* considered warnings:

```scss
//comment
```

```scss
///comment
```

## Further Reading

* [stylelint-scss - double-slash-comment-whitespace-inside](https://github.com/kristerkari/stylelint-scss/blob/master/src/rules/double-slash-comment-whitespace-inside)