Pattern: Use of `blank?` with safe navigation operator

Issue: -

## Description

This cop checks to make sure safe navigation isn't used with `blank?` in
a conditional.

While the safe navigation operator is generally a good idea, when
checking `foo&.blank?` in a conditional, `foo` being `nil` will actually
do the opposite of what the author intends.

## Examples

```ruby
# bad
do_something if foo&.blank?
do_something unless foo&.blank?

# good
do_something if foo.blank?
do_something unless foo.blank?
```

## Further Reading

* [RuboCop - Rails/SafeNavigationWithBlank](https://docs.rubocop.org/rubocop-rails/cops_rails.html)
