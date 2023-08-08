Pattern: Safe navigation with `empty?`

Issue: -

## Description

While the safe navigation operator is generally a good idea, when checking `foo&.empty?` in a conditional, `foo` being `nil` will actually do the opposite of what the author intends.

### Examples

```ruby
# bad
return if foo&.empty?
return unless foo&.empty?

# good
return if foo && foo.empty?
return unless foo && foo.empty?
```

## Further Reading

* [RuboCop - Lint/SafeNavigationWithEmpty](https://docs.rubocop.org/rubocop/cops_lint.html#lintsafenavigationwithempty)
