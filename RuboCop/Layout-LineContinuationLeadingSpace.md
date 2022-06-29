Pattern: Use of leading space for multi-lines

Issue: -

## Description

Checks that strings broken over multiple lines (by a backslash) contain trailing spaces instead of leading spaces.

## Examples

```ruby
# bad
'this text contains a lot of' \
'               spaces'

# good
'this text contains a lot of               ' \
'spaces'

# bad
'this text is too' \
' long'

# good
'this text is too ' \
'long'
```

## Further Reading

* [RuboCop - Layout/LineContinuationLeadingSpace](https://docs.rubocop.org/rubocop/cops_layout.html#layoutlinecontinuationleadingspace)
