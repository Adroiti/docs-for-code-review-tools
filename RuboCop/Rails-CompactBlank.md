Pattern: Missing use of `compact_blank`

Issue: -

## Description

Checks if collection can be blank-compacted with `compact_blank`.

## Examples

```ruby
# bad
collection.reject(&:blank?)
collection.reject { |_k, v| v.blank? }

# good
collection.compact_blank

# bad
collection.reject!(&:blank?)
collection.reject! { |_k, v| v.blank? }

# good
collection.compact_blank!
```

## Further Reading

* [RuboCop - Rails/CompactBlank](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railscompactblank)
