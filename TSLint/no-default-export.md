Pattern: Use of `default` export

Issue: -

## Description

Disallows `default` exports in ES6-style modules.  
  
Rationale: Named imports/exports [promote clarity](https://github.com/palantir/tslint/issues/1182#issue-151780453). In addition, current tooling differs on the correct way to handle `default` imports/exports. Avoiding them all together can help avoid tooling bugs and conflicts.

## Further Reading

* [TSLint - no-default-export](https://palantir.github.io/tslint/rules/no-default-export)