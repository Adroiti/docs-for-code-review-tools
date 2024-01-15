Pattern: Redundant predicate matcher

Issue: -

## Description

Checks for redundant predicate matcher.

## Examples

```ruby
# bad
expect(foo).to be_exist(bar)
expect(foo).not_to be_include(bar)
expect(foo).to be_all(bar)

# good
expect(foo).to exist(bar)
expect(foo).not_to include(bar)
expect(foo).to all be(bar)
```

## Further Reading

* [RSpec - RSpec/RedundantPredicateMatcher](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecredundantpredicatematcher)
