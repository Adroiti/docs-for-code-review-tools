Pattern: Use of `x == nil`

Issue: -

## Description

This rule checks for comparison of something with nil using `==`.

## Examples

```ruby
# bad
if x == nil

# good
if x.nil?
```

## Further Reading

* [RuboCop - Style/NilComparison](https://rubocop.readthedocs.io/en/latest/cops_style/#stylenilcomparison)
* [https://github.com/bbatsov/ruby-style-guide#predicate-methods](https://github.com/bbatsov/ruby-style-guide#predicate-methods)
