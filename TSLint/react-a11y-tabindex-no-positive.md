Pattern: Use of positive `tabindex`

Issue: -

## Description

For accessibility of your website, enforce `tabindex` value is not greater than zero. Avoid positive `tabindex` attribute values to synchronize the flow of the page with keyboard tab order.

## Further Reading

* [TSLint - react-a11y-tabindex-no-positive](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)
* [WCAG 2.4.3 - Focus Order](https://www.w3.org/TR/2008/REC-WCAG20-20081211/#navigation-mechanisms-focus-order)
* [Audit Rules - tabindex-usage](https://github.com/GoogleChrome/accessibility-developer-tools/wiki/Audit-Rules#tabindex-usage)
* [Avoid positive integer values for tabIndex](https://github.com/GoogleChrome/accessibility-developer-tools/wiki/Audit-Rules#ax_focus_03)