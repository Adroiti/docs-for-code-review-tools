Pattern: Unused variable

Issue: -

## Description

Unused local variables and unnecessary assigments increase code lines and decrease source code understanding.

```python
firstNumber = 100
secondNumber = 200

print secondNumber
print "firstNumber variable needs to be removed, because it's never used in the script"
```