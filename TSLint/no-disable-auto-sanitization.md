Pattern: Use of `execUnsafeLocalFunction`/`setInnerHTMLUnsafe` function

Issue: -

## Description

Do not disable auto-sanitization of HTML because this opens up your page
to an XSS attack. Specifically, do not use the [execUnsafeLocalFunction](https://msdn.microsoft.com/en-us/library/windows/apps/hh767331.aspx) or [setInnerHTMLUnsafe](https://msdn.microsoft.com/en-us/library/windows/apps/br211696.aspx) functions.

## Further Reading

* [TSLint - no-disable-auto-sanitization](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)