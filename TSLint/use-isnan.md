Pattern: Use isnan

Issue: -

## Description

Enforces use of the `isNaN()` function to check for NaN references instead of a comparison to the `NaN` constant.  
  
Rationale: Since `NaN !== NaN`, comparisons with regular operators will produce unexpected results. So, instead of `if (myVar === NaN)`, do `if (isNaN(myVar))`.

## Further Reading

* [TSLint - use-isnan](https://palantir.github.io/tslint/rules/use-isnan)