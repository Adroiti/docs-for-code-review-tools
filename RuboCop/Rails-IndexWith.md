Pattern: Missing use of `index_with`

Issue: -

## Description

This rule looks for uses of `each_with_object({}) { ... }`, `map { ... }.to_h`, and `Hash[map { ... }]` that are transforming an enumerable into a hash where the keys are the original elements. Rails provides the `index_with` method for this purpose.

## Examples

```ruby
# bad
[1, 2, 3].each_with_object({}) { |el, h| h[el] = foo(el) }
[1, 2, 3].map { |el| [el, foo(el)] }.to_h
Hash[[1, 2, 3].collect { |el| [el, foo(el)] }]

# good
[1, 2, 3].index_with { |el| foo(el) }
```

## Further Reading

* [RuboCop - Rails/IndexWith](https://docs.rubocop.org/projects/rails/en/stable/cops_rails/#railsindexwith)
