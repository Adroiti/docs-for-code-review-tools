Pattern: Unnecessary lambda

Issue: -

## Description

Used when the body of a lambda expression is a function call on the same argument list as the lambda itself; such lambda expressions are in all but a few cases replaceable with the function being called in the body of the lambda.


Example of **incorrect** code:

```python
results = " ".join(rdd.map(lambda x: save_and_show(x)).collect())
```

Example of **correct** code:

```python
results = " ".join(rdd.map(save_and_show).collect())
```
