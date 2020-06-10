Pattern: Missing use of `delete_prefix('prefix')`

Issue: -

## Description

In Ruby 2.5, `String#delete_prefix` has been added.

This rule identifies places where `gsub(/\Aprefix/, '')` and `sub(/\Aprefix/, '')` can be replaced by `delete_prefix('prefix')`.

This rule has `SafeMultiline` configuration option that true by default because `^prefix` is unsafe as it will behave incompatible with `delete_prefix` for receiver is multi-line string.

The `delete_prefix('prefix')` method is faster than `gsub(/\Aprefix/, '')`.

### Examples

```ruby
# bad
str.gsub(/\Aprefix/, '')
str.gsub!(/\Aprefix/, '')

str.sub(/\Aprefix/, '')
str.sub!(/\Aprefix/, '')

# good
str.delete_prefix('prefix')
str.delete_prefix!('prefix')
```

## Further Reading

* [RuboCop - Performance/DeletePrefix](https://docs.rubocop.org/rubocop-performance/cops_performance.html#performancedeleteprefix)
