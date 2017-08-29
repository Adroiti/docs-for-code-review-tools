Pattern: Misuse of `;`

Issue: -

## Description

This rule checks for:
- Missing space after `;`
- Semicolon defining empty statement. Use `{}` instead.
- Line containing only semicolon. If this should be an empty statement, use `{}` instead.
- Extra space before last `;`. If this should be an empty statement, use `{}` instead.

## Further Reading

* [Google C++ Style Guide - Horizontal Whitespace](https://google.github.io/styleguide/cppguide.html#Horizontal_Whitespace)