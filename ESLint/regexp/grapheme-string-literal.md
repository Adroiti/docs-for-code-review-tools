Pattern: String literal used for multiple graphemes

Issue: -

## Description

This rule is aimed to clarify the difference between using a string literal and normal disjunctions by not using string literals for purposes other than expressing a single grapheme.

## Examples

```js
/* eslint regexp/grapheme-string-literal: "error" */

/* ✓ GOOD */
var foo = /[\p{RGI_Emoji}--\q{🇦🇨|🇦🇩|🇦🇪|🇦🇫|🇦🇬|🇦🇮|🇦🇱|🇦🇲|🇦🇴|🇦🇶|🇦🇷|🇦🇸|🇦🇹|🇦🇺|🇦🇼|🇦🇽|🇦🇿|🇧🇦|🇧🇧|🇧🇩|🇧🇪|🇧🇫|🇧🇬|🇧🇭|🇧🇮|🇧🇯}]/v
var foo = /[\q{a|b|c}]/v

/* ✗ BAD */
var foo = /[\q{abc|def}]/v
```
