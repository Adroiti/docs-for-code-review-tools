Pattern: Use of `eval()`

Issue: -

## Description

Disallows `eval` function invocations.  
  
Rationale: `eval()` is dangerous as it allows arbitrary code execution with full privileges. There are [alternatives](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval) for most of the use cases for `eval()`.

## Further Reading

* [TSLint - no-eval](https://palantir.github.io/tslint/rules/no-eval)