Pattern: Missing use of `delete_suffix('suffix')`

Issue: -

## Description

In Ruby 2.5, `String#delete_suffix` has been added.

This rule identifies places where `gsub(/suffix\z/, '')` and `sub(/suffix\z/, '')` can be replaced by `delete_suffix('suffix')`.

This rule has `SafeMultiline` configuration option that true by default because `suffix$` is unsafe as it will behave incompatible with `delete_suffix?` for receiver is multi-line string.

The `delete_suffix('suffix')` method is faster than `gsub(/suffix\z/, '')`.

### Examples

```ruby
# bad
str.gsub(/suffix\z/, '')
str.gsub!(/suffix\z/, '')

str.sub(/suffix\z/, '')
str.sub!(/suffix\z/, '')

# good
str.delete_suffix('suffix')
str.delete_suffix!('suffix')
```

## Further Reading

* [RuboCop - Performance/DeleteSuffix](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancedeletesuffix)
