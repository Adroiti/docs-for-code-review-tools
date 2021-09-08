Pattern: Unsafe assignment to `innerHTML` or `outerHTML`

Issue: -

## Description

This error message suggests that you are using an unsafe coding
pattern. Please do not simply assign variables to `innertHTML`,
as this might cause Cross-Site Scripting (XSS) vulnerabilities.
We encourage you to construct DOM nodes using `createElement`
and changing their attributes (e.g., `textContent`, `classList`) instead.

## Further Reading

* [GitHub - property](https://github.com/mozilla/eslint-plugin-no-unsanitized/blob/master/docs/rules/property.md)