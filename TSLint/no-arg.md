Pattern: No arg

Issue: -

## Description

Disallows use of `arguments.callee`.  
  
Rationale: Using `arguments.callee` makes various performance optimizations impossible. See [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/callee) for more details on why to avoid `arguments.callee`.

## Further Reading

* [TSLint - no-arg](https://palantir.github.io/tslint/rules/no-arg)