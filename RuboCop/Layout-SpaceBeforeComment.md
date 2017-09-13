Pattern: Layout/SpaceBeforeComment

Issue: -

## Description

This cop checks for missing space between a token and a comment on the
same line.

### Example

```ruby
# bad
1 + 1# this operation does ...

# good
1 + 1 # this operation does ...
```

## Further Reading

* [RuboCop - Layout/SpaceBeforeComment](https://rubocop.readthedocs.io/en/latest/cops_layout/#layoutspacebeforecomment)
