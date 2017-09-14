Pattern: Nil comparison

Issue: -

## Description

This cop checks for comparison of something with nil using ==.

### Example

```ruby
# bad
if x == nil

# good
if x.nil?
```

## Further Reading

* [RuboCop - Style/NilComparison](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenilcomparison)
* [https://github.com/bbatsov/ruby-style-guide#predicate-methods](https://github.com/bbatsov/ruby-style-guide#predicate-methods)
