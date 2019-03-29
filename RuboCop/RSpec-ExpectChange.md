Pattern: Inconsistent style of `change` matcher

Issue: -

## Description

Checks for consistent style of `change` matcher.

Enforces either passing object and attribute as arguments to the matcher or passing a block that reads the attribute value.

This rule can be configured using the `EnforcedStyle` option.

## Examples

#### `EnforcedStyle: block`

```ruby
# bad
expect(run).to change(Foo, :bar)

# good
expect(run).to change { Foo.bar }
```
#### `EnforcedStyle: method_call`

```ruby
# bad
expect(run).to change { Foo.bar }
expect(run).to change { foo.baz }

# good
expect(run).to change(Foo, :bar)
expect(run).to change(foo, :baz)
# also good when there are arguments or chained method calls
expect(run).to change { Foo.bar(:count) }
expect(run).to change { user.reload.name }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `method_call` | `method_call`, `block`

## Further Reading

* [RSpec - RSpec/ExpectChange](https://rubocop-rspec.readthedocs.io/en/latest/cops_rspec/#rspecexpectchange)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectChange](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/ExpectChange)
