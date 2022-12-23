Pattern: Missing use of `Array#push(item)`

Issue: -

## Description

Enforces the use of `Array#push(item)` instead of `Array#concat([item])` to avoid redundant array literals.

## Examples

```ruby
# bad
list.concat([foo])
list.concat([bar, baz])
list.concat([qux, quux], [corge])

# good
list.push(foo)
list.push(bar, baz)
list.push(qux, quux, corge)
```

## Further Reading

* [RuboCop - Style/ConcatArrayLiterals](https://docs.rubocop.org/rubocop/cops_style.html#styleconcatarrayliterals)
