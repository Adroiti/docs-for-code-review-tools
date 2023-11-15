Pattern: Malformed ARIA role or attribute

Issue: -

## Description

For accessibility of your website, enforce that elements with explicit
or implicit roles defined contain only `aria-*` properties supported by
that `role`. Many ARIA attributes (states and properties) can only be
used on elements with particular roles. Some elements have implicit
roles, such as `<a href='hrefValue' />`, which will be resolved to `role='link'`.

## Further Reading

* [TSLint - react-a11y-role-supports-aria-props](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
* [Default Implicit ARIA Semantics](https://www.w3.org/TR/html-aria/#sec-strong-native-semantics)