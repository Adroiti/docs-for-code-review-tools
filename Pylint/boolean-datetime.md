Pattern: Datetime used in boolean context

Issue: -

## Description

Using `datetime.time` in a boolean context can hide subtle bugs when the time they represent matches midnight UTC. This behavior was fixed in Python 3.5. This message can't be emitted when using Python >= 3.5.

## Further Reading

* [Python - Issue13936](http://bugs.python.org/issue13936)
