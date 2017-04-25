Pattern: Name will become a keyword

Issue: -

## Description

Emitted when used name is known to become a keyword in future Python release. Assignments to keywords would result in `SyntaxError` after switching to newer interpreter version. 


Examples:

```python
# While it's correct in Python 2.x, it raises a SyntaxError in Python 3.x
True = 1
False = 0

# Same as above, but it'll be a SyntaxError starting from Python 3.7
async = "async"
await = "await
```
