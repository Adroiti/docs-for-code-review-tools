Pattern: Use of default import

Issue: -

## Description

Disallows importing default members from certain ES6-style modules. Import named members instead.
  
Rationale: Named imports/exports [promote clarity](https://github.com/palantir/tslint/issues/1182#issue-151780453). In addition, current tooling differs on the correct way to handle default imports/exports. Avoiding them all together can help avoid tooling bugs and conflicts.

## Further Reading

* [TSLint - no-default-import](https://palantir.github.io/tslint/rules/no-default-import)