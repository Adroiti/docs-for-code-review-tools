Pattern: Use of `eval()`

Issue: -

## Description

Used when you use the `eval()` function, to discourage its usage. It's usage may have negative readability, performance and security implications, especially if you accept strings from untrusted or unknown sources. Consider using `ast.literal_eval()` for safely evaluating strings containing expressions from untrusted sources.


Example of **incorrect** code:

```python
eval('os.listdir(".")')
```

Example of **correct** code:

```python
ast.literal_eval('os.listdir(".")')
```

## Further Reading

* [The Python Standard Library - eval()](https://docs.python.org/2/library/functions.html#eval)
* [Ned Batchelder - Eval really is dangerous](https://nedbatchelder.com/blog/201206/eval_really_is_dangerous.html)
