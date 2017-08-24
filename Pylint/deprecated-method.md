Pattern: Deprecated method

Issue: -

## Description

The method is marked as deprecated and will be removed in a future version of Python. Consider looking for an alternative in the documentation.


Example of **incorrect** code:

```python
status = os.system("mycmd" + " myarg")
```

Example of **correct** code:

```python
status = subprocess.call("mycmd" + " myarg", shell=True)
```

## Further Reading

* [The Python Standard Library - Updating Code For New Versions of Python](https://docs.python.org/2/library/warnings.html#updating-code-for-new-versions-of-python)
* [The Python Standard Library - Replacing Older Functions with the subprocess Module](https://docs.python.org/2/library/subprocess.html#subprocess-replacements)
