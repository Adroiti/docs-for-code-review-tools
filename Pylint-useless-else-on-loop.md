Pattern: Useless `else` on loop

Issue: -

## Description

The `else` clause of a loop is executed when the loop sequence is empty. When a loop specifies no `break` statement the loop sequence will eventually always become empty and `else` clause will always execute. You can ignore this issue if this is the intended behavior.


If the `else` clause should not always execute at the end of a loop clause, then the code should add a `break` statement within the loop block.


Example of **incorrect** code:

```python
def even_test():
    for i in range(10):
        if i % 2:
            print("number is even")
    else:  # [useless-else-on-loop]
        print("list is empty")
```

Example of **correct** code:

```python
def even_test():
    for i in range(10):
        if i % 2:
            print("number is even")
            break
    else:
        print("list is empty")
```
