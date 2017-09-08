Pattern: Restricted submodule import

Issue: -

## Description

Disallows importing any submodule.  
  
Rationale: Submodules of some packages are treated as private APIs and the import paths may change without deprecation periods. It’s best to stick with top-level package exports.

## Further Reading

* [TSLint - no-submodule-imports](https://palantir.github.io/tslint/rules/no-submodule-imports)