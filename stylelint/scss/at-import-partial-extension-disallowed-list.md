Pattern: Disallowed file extension in `@import`

Issue: -

## Description

Specify a list of disallowed file extensions for partial names in `@import` commands.

```scss
@import "file.scss"
/**           ↑
 * Disallowed list of these */
```

The rule ignores [cases](https://sass-lang.com/documentation/at-rules/import) when Sass considers an `@import` command just a plain CSS import:

* If the file’s extension is `.css`.
* If the filename begins with `http://` (or any other protocol).
* If the filename is a `url()`.
* If the `@import` has any media queries.

## Examples

`array`: `["array", "of", "extensions"]`

Each value is either a string or a regexp.

Given:

```js
["scss", /less/]
```

The following patterns are considered warnings:

```scss
@import "foo.scss";
```

```scss
@import "path/fff.less";
```

```scss
@import "path\\fff.ruthless";
```

```scss
@import "df/fff", '1.SCSS';
```

The following patterns are *not* considered warnings:

```scss
@import "path/fff";
```

```scss
@import url("path/_file.css"); /* has url(), so doesn't count as a partial @import */
```

```scss
@import "file.css"; /* Has ".css" extension, so doesn't count as a partial @import */
```

```scss
/* Both are URIs, so don't count as partial @imports */
@import "http://_file.scss";
@import "//_file.scss";
```

```scss
@import "file.scss" screen; /* Has a media query, so doesn't count as a partial @import */
```

## Further Reading

* [stylelint-scss - at-import-partial-extension-disallowed-list](https://github.com/stylelint-scss/stylelint-scss/tree/master/src/rules/at-import-partial-extension-disallowed-list)