Pattern: Use of `Array.new`/`Hash.new`/`String.new`

Issue: -

## Description

This rule checks for the use of a method, the result of which would be a literal, like an empty array, hash or string.

## Examples

```ruby
# bad
arr = Array.new
hash = Hash.new

# good
arr = []
arr = Array.new(10)
hash = {}
hash = Hash.new(0)
```

## Further Reading

* [RuboCop - Style/EmptyLiteral](https://docs.rubocop.org/rubocop/cops_style.html#styleemptyliteral)
* [https://github.com/bbatsov/ruby-style-guide#literal-array-hash](https://github.com/bbatsov/ruby-style-guide#literal-array-hash)
