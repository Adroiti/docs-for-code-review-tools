Pattern: Insecure write of HTML

Issue: -

## Description

Do not write values to `innerHTML`, `outerHTML`, or set HTML using the
JQuery html() function. Writing values to `innerHTML` can expose your
website to XSS injection attacks. All strings must be escaped before
being rendered to the page.

## Further Reading

* [TSLint - no-inner-html](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)