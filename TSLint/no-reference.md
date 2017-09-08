Pattern: Use of `<reference>` import

Issue: -

## Description

Disallows `/// <reference path=>` imports (use ES6-style imports instead).  
  
Rationale: Using `/// <reference path=>` comments to load other files is outdated. Use ES6-style imports to reference other files.

## Further Reading

* [TSLint - no-reference](https://palantir.github.io/tslint/rules/no-reference)