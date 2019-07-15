Pattern: Use of non-primitive comparison

Issue: -

## Description

Only allow comparisons between primitives.
  
Rationale: When using comparison operators to compare objects, they compare references and not values. This is often done accidentally. With this rule, `>`, `>=`, `<`, `<=` operators are only allowed when comparing `numbers`. `===`, `!==` are allowed for `number` `string` and `boolean` types and if one of the operands is `null` or `undefined`.

## Further Reading

* [TSLint - strict-comparisons](https://palantir.github.io/tslint/rules/strict-comparisons)