Pattern: Missing use of implicit booleaness

Issue: -

## Description

Emitted when collection literal comparison is being used to check for emptiness. Use implicit booleaness instead of a collection classes. Empty collections are considered as false.


Example of **incorrect** code:

```python
if data == {}:
    print("This will be printed")
if data != {}:
    print("This will also be printed")
```

Example of **correct** code:

```python
if data or not data:
    print("This however won't be")
```
