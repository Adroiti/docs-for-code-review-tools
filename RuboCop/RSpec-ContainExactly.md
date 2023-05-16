Pattern: Use of `contain_exactly`

Issue: -

## Description

Checks where `contain_exactly` is used.

This rule checks for the following:
- Prefer `match_array` when matching array values.
- Prefer `be_empty` when using `contain_exactly` with no arguments.

## Examples

```ruby
# bad
it { is_expected.to contain_exactly(*array1, *array2) }

# good
it { is_expected.to match_array(array1 + array2) }

# good
it { is_expected.to contain_exactly(content, *array) }
```

## Further Reading

* [RSpec - RSpec/ContainExactly](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspeccontainexactly)
