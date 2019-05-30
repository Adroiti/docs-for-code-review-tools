Pattern: Reassigning constant parameter

Issue: -

## Description

Disallows reassigning parameters that are considered constants.

## Examples

```ts
function fn(/**@const*/foo, bar) {
  foo++; // error on this line
  bar++; // no error
}

class C {
  constructor(/** @const */ public foo) {
    foo++; // error on this line
    this.foo++; // no error on this line, because only parameters are checked by this rule
  }
}

function fn(/**@constant*/foo) { // also works with @constant tag
  foo++; // error on this line
}

function fn({ // also works with destructured parameters
  /**@const*/ foo,
  baz: /**@const*/ bar,
}) {
  foo++; // error on this line
  bar++; // error on this line
}
```

## Further Reading

* [TSLint - const-parameters](https://github.com/ajafff/tslint-consistent-codestyle/blob/master/docs/const-parameters.md)