Pattern: Malformed line continuation spacing

Issue: -

## Description

Checks that the backslash of a line continuation is separated from preceding text by exactly one space (default) or zero spaces.

## Examples

### EnforcedStyle: space (default)

```ruby
# bad
'a'\
'b'  \
'c'

# good
'a' \
'b' \
'c'
```

## Further Reading

* [RuboCop - Layout/LineContinuationSpacing](https://docs.rubocop.org/rubocop/cops_layout.html#layoutlinecontinuationspacing)
