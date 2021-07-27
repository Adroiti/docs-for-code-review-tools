Pattern: Unsafe call to `insertAdjacentHTML`, `document.write` or `document.writeln`

Issue: -

## Description

This error message suggests that you are using an unsafe coding
pattern. Please do not simply call functions like `insertAdjacentHTML` with a
variable parameter, as this might cause Cross-Site Scripting (XSS)
vulnerabilities. We encourage you to construct DOM nodes using `createElement`
and changing their attributes (e.g., `textContent`, `classList`) instead.

## Further Reading

* [GitHub - method](https://github.com/mozilla/eslint-plugin-no-unsanitized/blob/master/docs/rules/method.md)