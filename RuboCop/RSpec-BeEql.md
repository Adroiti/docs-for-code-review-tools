Pattern: Missing use of `be(...)`

Issue: -

## Description

Checks for expectations where `be(...)` can replace `eql(...)`.

The `be` matcher compares by identity while the `eql` matcher
compares using `eql?`. Integers, floats, booleans, symbols, and nil
can be compared by identity and therefore the `be` matcher is
preferable as it is a more strict test.

This rule only looks for instances of `expect(...).to eql(...)`. We
do not check `to_not` or `not_to` since `!eql?` is more strict
than `!equal?`. We also do not try to flag `eq` because if
`a == b`, and `b` is comparable by identity, `a` is still not
necessarily the same type as `b` since the `#==` operator can
coerce objects for comparison.

## Examples

```ruby
# bad
expect(foo).to eql(1)
expect(foo).to eql(1.0)
expect(foo).to eql(true)
expect(foo).to eql(false)
expect(foo).to eql(:bar)
expect(foo).to eql(nil)

# good
expect(foo).to be(1)
expect(foo).to be(1.0)
expect(foo).to be(true)
expect(foo).to be(false)
expect(foo).to be(:bar)
expect(foo).to be(nil)
```

## Further Reading

* [RSpec - RSpec/BeEql](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecbeeql)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/BeEql](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/BeEql)
