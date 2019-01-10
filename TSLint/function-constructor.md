Pattern: Use of built-in Function constructor

Issue: -

## Description

Prevents using the built-in Function constructor.  
  
Rationale: Calling the constructor directly is similar to `eval`, which is a symptom of design issues. String inputs don’t receive type checking and can cause performance issues, particularly when dynamically created.

## Further Reading

* [TSLint - function-constructor](https://palantir.github.io/tslint/rules/function-constructor)