Pattern: Undefined loop variable

Issue: -

## Description

Avoid using loop variable outside of loop as it might be undefined. This may lead to unexpected behavior and source of bugs.


Example of **incorrect** code:

```python
def do_stuff(some_random_list):
    for i in some_random_list:
        print i
    print i  # [undefined-loop-variable]
```

Example of **correct** code:

```python
def do_stuff(some_random_list):
    for i in some_random_list:
        print i
```
