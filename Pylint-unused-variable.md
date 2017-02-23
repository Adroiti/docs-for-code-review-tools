Pattern: Unused variable

Issue: -

## Description

Unused local variables increase code lines and decrease understanding of source code. In some cases unused variables is the result of unimplemented functionality that developer forgets to do, in that case ticket should be created to remind what to do later. 

Example of <b>incorrect</b> code:
```python
number = 100

print "Program contains unused variable"
```

Example of <b>correct</b> code:
```python
number = 100

print number;
```
