Pattern: Use of `pluck(…​).first` instead of `pick`

Issue: -

## Description

This rule enforces the use `pick` over `pluck(…​).first`.

## Examples

```ruby
# bad
Model.pluck(:a).first
Model.pluck(:a, :b).first

# good
Model.pick(:a)
Model.pick(:a, :b)
```

## Further Reading

* [RuboCop - Rails/Pick](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railspick)
