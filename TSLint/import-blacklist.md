Pattern: Import blacklist

Issue: -

## Description

Disallows importing the specified modules directly via `import` and `require`. Instead only sub modules may be imported from that module.  
  
Rationale: Some libraries allow importing their submodules instead of the entire module. This is good practise as it avoids loading unused modules.

## Further Reading

* [TSLint - import-blacklist](https://palantir.github.io/tslint/rules/import-blacklist)