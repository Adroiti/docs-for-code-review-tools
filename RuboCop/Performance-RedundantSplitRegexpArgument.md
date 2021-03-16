Pattern: Redundant `split` Regexp argument

Issue: -

## Description

Identifies places where `split` argument can be replaced from a deterministic regexp to a string.

## Examples

```ruby
# bad
'a,b,c'.split(/,/)

# good
'a,b,c'.split(',')
```

## Further Reading

* [RuboCop - Performance/RedundantSplitRegexpArgument](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performanceredundantsplitregexpargument)
