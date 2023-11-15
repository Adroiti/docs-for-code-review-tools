Pattern: Missing `alt` for `img` element

Issue: -

## Description

Enforce that an `img` element contains the `alt` attribute or
`role='presentation'` for a decorative image. All images must have `alt`
text to convey their purpose and meaning to screen reader users.
Besides, the `alt` attribute specifies an alternate text for an image,
if the image cannot be displayed.  

## Configuration

This rule accepts as a parameter a string array for tag names other than
`img` to also check. For example, if you use a custom tag named `Image`
then configure the rule with: `[true, ['Image']]`.

## Further Reading

* [TSLint - react-a11y-img-has-alt](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
* [Web Content Accessibility Guidelines 1.0](https://www.w3.org/TR/WCAG10/wai-pageauth.html#tech-text-equivalent)