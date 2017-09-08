Pattern: `import` with side-effect

Issue: -

## Description

Avoid import statements with side-effect.  
  
Rationale: Imports with side effects may have behavior which is hard for static verification.

## Further Reading

* [TSLint - no-import-side-effect](https://palantir.github.io/tslint/rules/no-import-side-effect)