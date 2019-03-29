Pattern: Malformed use of `create_list`

Issue: -

## Description

Checks for `create_list` usage.

This cop can be configured using the `EnforcedStyle` option

## Examples

#### `EnforcedStyle: create_list`

```ruby
# bad
3.times { create :user }

# good
create_list :user, 3

# good
3.times { |n| create :user, created_at: n.months.ago }
```
#### `EnforcedStyle: n_times`

```ruby
# bad
create_list :user, 3

# good
3.times { create :user }
```

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `create_list` | `create_list`, `n_times`

## Further Reading

* [RSpec - FactoryBot/CreateList](https://rubocop-rspec.readthedocs.io/en/latest/cops_factorybot/#factorybotcreatelist)
* [http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/FactoryBot/CreateList](http://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/FactoryBot/CreateList)
