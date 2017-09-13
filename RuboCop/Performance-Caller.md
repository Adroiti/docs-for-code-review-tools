Pattern: Performance/Caller

Issue: -

## Description

This cop identifies places where `caller[n]`
can be replaced by `caller(n..n).first`.

### Example

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
