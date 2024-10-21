Pattern: Missing use of `pluck(:column_name)`

Issue: -

## Description

Checks for uses of `select(:column_name)` with `map(&:column_name)`. These can be replaced with `pluck(:column_name)`.

There also should be some performance improvement since it skips instantiating the model class for matches.


## Examples

```ruby
# bad
Model.select(:column_name).map(&:column_name)

# good
Model.pluck(:column_name)
```

## Further Reading

* [RuboCop - Rails/SelectMap](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsselectmap)
