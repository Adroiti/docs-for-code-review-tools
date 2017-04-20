Pattern: Use of insecure `input()` function

Issue: -

## Description

The `input()` function in Python 2 will read from standard input, evaluate and run
the resulting string as python source code. This is similar, though in many
ways worse, then using eval. On Python 2, use `raw_input()` instead, input is safe
in Python 3.


Example of **incorrect** code:

```python
name = input("What's your name? ")
print("Nice to meet you " + name + "!")
```

Example of **correct** code:

```python
name = raw_input("What's your name? ")
print("Nice to meet you " + name + "!")
```

## Further Reading]

* [The Python Standard Library - input()](https://docs.python.org/2/library/functions.html#input)
* [OpenStack - B322: input](https://docs.openstack.org/developer/bandit/api/bandit.blacklists.html#b322-input)
