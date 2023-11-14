Pattern: Missing use of `eq`

Issue: -

## Description

Use `eq` instead of `be ==` to compare objects.

## Examples

```ruby
# bad
# bad
expect(foo).to be == 42

# good
expect(foo).to eq 42
```

## Further Reading

* [RSpec - RSpec/Eq](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspeceq)
