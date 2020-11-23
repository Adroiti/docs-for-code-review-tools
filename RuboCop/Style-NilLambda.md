Pattern: Nil lambda

Issue: -

## Description

Checks for lambdas that always return nil, which can be replaced with an empty lambda instead.

## Examples

```ruby
# bad
-> { nil }

lambda do
  next nil
end

# good
-> {}

lambda do
end

-> (x) { nil if x }
```

## Further Reading

* [RuboCop - Style/NilLambda](https://docs.rubocop.org/rubocop/cops_style.html#stylenillambda)
