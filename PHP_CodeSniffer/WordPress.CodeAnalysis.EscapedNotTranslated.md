Pattern: Use of escaping function with more than one parameter

Issue: -

## Description

Flags calls to escaping functions which look like they may have been intended
as calls to the "translate + escape" sister-function due to the presence of
more than one parameter.

## Further Reading

* [WordPress.CodeAnalysis.EscapedNotTranslated](https://github.com/WordPress/WordPress-Coding-Standards/blob/develop/WordPress/Sniffs/CodeAnalysis/EscapedNotTranslatedSniff.php)