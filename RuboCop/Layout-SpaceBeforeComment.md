Pattern: Missing space before comment

Issue: -

## Description

This rule checks for missing space between a token and a comment on the same line.

## Examples

```ruby
# bad
1 + 1# this operation does ...

# good
1 + 1 # this operation does ...
```

## Further Reading

* [RuboCop - Layout/SpaceBeforeComment](https://docs.rubocop.org/rubocop/cops_layout.html#layoutspacebeforecomment)
