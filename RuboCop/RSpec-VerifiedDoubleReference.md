Pattern: Inconsistent style for verified double reference

Issue: -

## Description

Checks for consistent verified double reference style.

Only investigates references that are one of the supported styles.

This rule can be configured in your configuration using the
`EnforcedStyle` option and supports `--auto-gen-config`.

## Examples

#### `EnforcedStyle: constant` (default)

```ruby
# bad
let(:foo) do
  instance_double('ClassName', method_name: 'returned_value')
end

# good
let(:foo) do
  instance_double(ClassName, method_name: 'returned_value')
end
```

#### `EnforcedStyle: string`

```ruby
# bad
let(:foo) do
  instance_double(ClassName, method_name: 'returned_value')
end

# good
let(:foo) do
  instance_double('ClassName', method_name: 'returned_value')
end
```

#### Reference is not in the supported style list. No enforcement

```ruby
# good
let(:foo) do
  instance_double(@klass, method_name: 'returned_value')
end
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `constant` | `constant`, `string`

## Further Reading

* [RSpec - RSpec/VerifiedDoubleReference](https://docs.rubocop.org/rubocop-rspec/cops_rspec.html#rspecverifieddoublereference)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/VerifiedDoubleReference