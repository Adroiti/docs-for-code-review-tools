Pattern: Missing radix parameter

Issue: -

## Description

Requires the radix parameter to be specified when calling `parseInt`.  
  
Rationale: Always specify this parameter to eliminate reader confusion and to guarantee predictable behavior. Different implementations produce different results when a radix is not specified, usually defaulting the value to 10.

## Further Reading

* [TSLint - radix](https://palantir.github.io/tslint/rules/radix)
* [MDN web docs - parseInt()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)