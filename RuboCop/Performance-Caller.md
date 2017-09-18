Pattern: Use of `caller[n]` instead of `caller(n..n).first`

Issue: -

## Description

This rule identifies places where `caller[n]` can be replaced by `caller(n..n).first`.

## Examples

```ruby
# bad
caller[1]
caller.first
caller_locations[1]
caller_locations.first

# good
caller(2..2).first
caller(1..1).first
caller_locations(2..2).first
caller_locations(1..1).first
```

## Further Reading

* [RuboCop - Performance/Caller](https://rubocop.readthedocs.io/en/latest/cops_performance/#performancecaller)
