Pattern: Inconsistent hook argument

Issue: -

## Description

Checks the arguments passed to `before`, `around`, and `after`.

This rule checks for consistent style when specifying RSpec
hooks which run for each example. There are three supported
styles: "implicit", "each", and "example." All styles have
the same behavior.

## Examples

#### when configuration is `EnforcedStyle: implicit`

```ruby
# bad
before(:each) do
  # ...
end

# bad
before(:example) do
  # ...
end

# good
before do
  # ...
end
```
#### when configuration is `EnforcedStyle: each`

```ruby
# bad
before(:example) do
  # ...
end

# good
before do
  # ...
end

# good
before(:each) do
  # ...
end
```
#### when configuration is `EnforcedStyle: example`

```ruby
# bad
before(:each) do
  # ...
end

# bad
before do
  # ...
end

# good
before(:example) do
  # ...
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `implicit` | `implicit`, `each`, `example`

## Further Reading

* [RSpec - RSpec/HookArgument](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspechookargument)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/HookArgument](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/HookArgument)
