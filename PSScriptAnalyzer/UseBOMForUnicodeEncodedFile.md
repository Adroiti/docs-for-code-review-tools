Pattern: Missing Byte Order Mark for non-ASCII encoded file

Issue: -

## Description

For a file encoded with a format other than ASCII, ensure Byte Order Mark (BOM) is present to ensure that any application consuming this file can interpret it correctly.

## How

Ensure that the file is encoded with BOM present.

## Further Reading

* [PSScriptAnalyzer - UseBOMForUnicodeEncodedFile](https://github.com/PowerShell/PSScriptAnalyzer/blob/master/RuleDocumentation/UseBOMForUnicodeEncodedFile.md)