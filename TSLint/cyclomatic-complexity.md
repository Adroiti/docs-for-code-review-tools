Pattern: High cyclomatic complexity

Issue: -

## Description

Enforces a threshold of cyclomatic complexity.

Cyclomatic complexity is assessed for each function of any type. A starting value of 0 is assigned and this value is then incremented for every statement which can branch the control flow within the function. The following statements and expressions contribute to cyclomatic complexity:

  - `catch`
  - `if` and `? :`
  - `||` and `&&` due to short-circuit evaluation
  - `for`, `for in` and `for of` loops
  - `while` and `do while` loops
  - `case` clauses that contain statements
  
Rationale: Cyclomatic complexity is a code metric which indicates the level of complexity in a function. High cyclomatic complexity indicates confusing code which may be prone to errors or difficult to modify.

## Further Reading

* [TSLint - cyclomatic-complexity](https://palantir.github.io/tslint/rules/cyclomatic-complexity)