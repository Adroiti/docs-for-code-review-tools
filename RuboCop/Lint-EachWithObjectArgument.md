Pattern: Immutable argument to `each_with_object`

Issue: -

## Description

This rule checks if `each_with_object` is called with an immutable
argument. Since the argument is the object that the given block shall
make calls on to build something based on the enumerable that
`each_with_object` iterates over, an immutable argument makes no sense.

## Examples

```ruby
# bad

sum = numbers.each_with_object(0) { |e, a| a += e }
```
```ruby
# good

num = 0
sum = numbers.each_with_object(num) { |e, a| a += e }
```

## Further Reading

* [RuboCop - Lint/EachWithObjectArgument](https://docs.rubocop.org/rubocop/cops_lint.html#linteachwithobjectargument)
