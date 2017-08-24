Pattern: Unused variable

Issue: -

## Description

Variables that are declared and not used anywhere in the code are most likely an error resulting from incomplete refactoring. Such variables take up space in the code and can lead to confusion by readers. Use or remove them to resolve this issue.


Example of **incorrect** code:
```python
number = 100

print "Program contains unused variable"
```

Example of **correct** code:
```python
number = 100

print number;
```