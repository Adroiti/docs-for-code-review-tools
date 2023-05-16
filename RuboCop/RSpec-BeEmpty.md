Pattern: Missing use of `be_empty`

Issue: -

## Description

Prefer using `be_empty` when checking for an empty array.

## Examples

```ruby
# bad
expect(array).to contain_exactly
expect(array).to match_array([])

# good
expect(array).to be_empty
```

## Further Reading

* [RSpec - RSpec/BeEmpty](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecbeempty)
