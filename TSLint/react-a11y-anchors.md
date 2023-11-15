Pattern: Malformed anchor tag

Issue: -

## Description

For accessibility of your website, anchor element link text should be at
least 4 characters long. Links with the same HREF should have the same
link text. Links that point to different HREFs should have different
link text. 

## Configuration

This can be relaxed to allow differences in cases using
`ignore-case` option. You can also allow differences in leading/trailing
whitespace by adding `{"ignore-whitespace": "trim"}` option or all
whitespace by adding `{"ignore-whitespace": "all"}` option. Links with
images and text content, the alt attribute should be unique to the text
content or empty. An an anchor element's href prop value must not be
undefined, null, or just `#`.

## Further Reading

* [TSLit - react-a11y-anchors](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)