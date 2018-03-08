Pattern: Use of `StopIteration` in generator

Issue: -

## Description

According to _PEP 479_, the raise of `StopIteration` to end the loop of a generator may lead to hard to find bugs. This PEP specify that `raise StopIteration` could be replaced by a simple return statement.

## Further Reading

* [PEP 479 -- Change StopIteration handling inside generators](http://legacy.python.org/dev/peps/pep-0479/#making-return-triggered-stopiterations-obvious)