Pattern: Use of `object_id` for key

Issue: -

## Description

Prefer using `Hash#compare_by_identity` than using `object_id` for hash keys.

## Examples

```ruby
# bad
hash = {}
hash[foo.object_id] = :bar
hash.key?(baz.object_id)

# good
hash = {}.compare_by_identity
hash[foo] = :bar
hash.key?(baz)
```

## Further Reading

* [RuboCop - Lint/HashCompareByIdentity](https://docs.rubocop.org/rubocop/cops_lint.html#linthashcomparebyidentity)
