Pattern: Misleading backtick at end of line

Issue: -

## Description

Ending a line with an escaped whitespace character is misleading. A trailing backtick is usually used for line continuation. Users typically don't intend to end a line with escaped whitespace.

## Further Reading

* [PSScriptAnalyzer - MisleadingBacktick](https://github.com/PowerShell/PSScriptAnalyzer/tree/master/docs/Rules/MisleadingBacktick.md)