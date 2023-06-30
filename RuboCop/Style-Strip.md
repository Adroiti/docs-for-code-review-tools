Pattern: Use of `lstrip.rstrip` instead of `strip`

Issue: -

## Description

This rule identifies places where `lstrip.rstrip` can be replaced by `strip`.

## Examples

```ruby
# bad
'abc'.lstrip.rstrip
'abc'.rstrip.lstrip

# good
'abc'.strip
```
