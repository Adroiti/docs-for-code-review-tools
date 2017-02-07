Pattern: Avoid using exec() when possible

Issue: -

## Description

The `exec` statement is dangerous, hard to test, and hard to read. Avoid it, as much as possible. This is largery due to the fact that exec() enables you to dynamically execute arbitrary Python code which is stored in literal strings. Consider going back to the code to check if there is a clearer, more direct way to accomplish the task.

Example of **incorrect** code:

```python
text = "print \"Hello, World!\""
exec text
```

Example of **correct** code:

```python
def foo():
    print "Hello, World!"
    
foo()
```

## Further Reading

* [Pylint - W0122](http://pylint-messages.wikidot.com/messages:w0122)
