Pattern: Inconsistent style when matching `nil`

Issue: -

## Description

Ensures a consistent style is used when matching `nil`.

You can either use the more specific `be_nil` matcher, or the more
generic `be` matcher with a `nil` argument.

This rule can be configured using the `EnforcedStyle` option

## Examples

#### `EnforcedStyle: be_nil` (default)

```ruby
# bad
expect(foo).to be(nil)

# good
expect(foo).to be_nil
```

#### `EnforcedStyle: be`

```ruby
# bad
expect(foo).to be_nil

# good
expect(foo).to be(nil)
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `be_nil` | `be`, `be_nil`

## Further Reading

* [RSpec - RSpec/BeNil](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecbenil)