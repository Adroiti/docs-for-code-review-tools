Pattern: Missing safe navigation operator (`&.`)

Issue: -

## Description

This rule converts usages of `try!` to `&.`. It can also be configured
to convert `try`. It will convert code to use safe navigation if the
target Ruby version is set to 2.3+

## Examples

```ruby
# ConvertTry: false
  # bad
  foo.try!(:bar)
  foo.try!(:bar, baz)
  foo.try!(:bar) { |e| e.baz }

  foo.try!(:[], 0)

  # good
  foo.try(:bar)
  foo.try(:bar, baz)
  foo.try(:bar) { |e| e.baz }

  foo&.bar
  foo&.bar(baz)
  foo&.bar { |e| e.baz }

# ConvertTry: true
  # bad
  foo.try!(:bar)
  foo.try!(:bar, baz)
  foo.try!(:bar) { |e| e.baz }
  foo.try(:bar)
  foo.try(:bar, baz)
  foo.try(:bar) { |e| e.baz }

  # good
  foo&.bar
  foo&.bar(baz)
  foo&.bar { |e| e.baz }
```

## Default configuration

Attribute | Value
--- | ---
ConvertTry | false

## Further Reading

* [RuboCop - Rails/SafeNavigation](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railssafenavigation)
