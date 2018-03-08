Pattern: Malformed formatted message for raised exception

Issue: -

## Description

Emitted when passing multiple arguments to an exception constructor, the first of them a string literal containing what appears to be placeholders intended for formatting.

This warning can be ignored on projects which deliberately use lazy formatting of messages in all user-facing exception handlers.

Example of **incorrect** code:

```python
raise SomeError('message about %s', foo)
raise SomeError('message about {}', foo)
```

Example of **correct** code:

```python
def good_case():
raise SomeError('message about %s' % foo)
raise SomeError('message about {}'.format(foo))
```