Pattern: Style/ZeroLengthPredicate

Issue: -

## Description

This cop checks for numeric comparisons that can be replaced
by a predicate method, such as receiver.length == 0,
receiver.length > 0, receiver.length != 0,
receiver.length < 1 and receiver.size == 0 that can be
replaced by receiver.empty? and !receiver.empty.

### Example

```ruby
# bad
[1, 2, 3].length == 0
0 == "foobar".length
array.length < 1
{a: 1, b: 2}.length != 0
string.length > 0
hash.size > 0

# good
[1, 2, 3].empty?
"foobar".empty?
array.empty?
!{a: 1, b: 2}.empty?
!string.empty?
!hash.empty?
```

## Further Reading

* [RuboCop - Style/ZeroLengthPredicate](https://rubocop.readthedocs.io/en/latest/cops_style/#stylezerolengthpredicate)
