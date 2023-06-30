Pattern: Unnecessary `;`

Issue: -

## Description

Semicolons are not necessary in Python unless you are putting more than one statement in a line. This is a style slip-up that's particularly easy to make for old hands of other programming languages such as C or Perl, where semicolons are always (or almost always) required after each statement.


Example of **incorrect** code:

```python
__revision__.lower();
```

Example of **correct** code:

```python
__revision__.lower()
```
