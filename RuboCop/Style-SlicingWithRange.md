Pattern: Use of `ary[n..-1]` instead of `ary[n..]`

Issue: -

## Description

This rule checks that arrays are sliced with endless ranges instead of `ary[start..-1]` on Ruby 2.6+.

## Examples

```ruby
# bad
items[1..-1]

# good
items[1..]
```

## Further Reading

* [RuboCop - Layout/SlicingWithRange](https://docs.rubocop.org/rubocop/cops_style.html#styleslicingwithrange)
