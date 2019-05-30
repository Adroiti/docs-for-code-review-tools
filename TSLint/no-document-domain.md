Pattern: Writing to `document.domain`

Issue: -

## Description

Do not write to `document.domain`. Scripts setting document.domain to
any value should be validated to ensure that the value is on a list of
allowed sites. Also, if your site deals with PII in any way then
document.domain must not be set to a top-level domain (for example,
live.com) but only to an appropriate subdomain (for example,
billing.live.com). If you are absolutely sure that you want to set
document.domain then add a tslint suppression comment for the line.

## Further Reading

* [TSLint - no-document-domain](https://github.com/microsoft/tslint-microsoft-contrib/blob/master/README.md#supported-rules)