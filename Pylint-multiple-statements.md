Pattern: Avoid multiple statements on a single line

Issue: -

## Description

Python syntax does permit more than one statement on a line, separated by semicolon (`;`). However, limiting each line to one statement makes it easier for a human to follow a program's logic when reading through it.


Compound statements are also discouraged by `PEP 8` style guide.


Example of **incorrect** code:

```python
if foo == 'blah': do_blah_thing()
do_one(); do_two(); do_three()
```

Example of **correct** code:

```python
if foo == 'blah':
    do_blah_thing()
do_one()
do_two()
do_three()
```

## Further Reading

* [PEP 8 - Whitespace in Expressions and Statements](https://www.python.org/dev/peps/pep-0008/#other-recommendations)
* [Pylint - C0321](http://pylint-messages.wikidot.com/messages:c0321)
