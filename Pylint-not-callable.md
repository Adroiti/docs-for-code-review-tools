Pattern: Avoid calling uncallable object

Issue: -

## Description

This issue is usually a result of name collision between class/method or module/function. Bacause of this a `TypeError` is raised at runtime. Fully qualify the called function or use more specific `import` statements to resolve this issue.


Example of **incorrect** code:

```python
import random

print(random()) # [not-callable]
```

Examples of **correct** code:

```python
from random import random # more specific import statement

print(random())
print(random.random()) # fully qualified function
```

## Further Reading

* [Pylint - E1102](http://pylint-messages.wikidot.com/messages:e1102)
