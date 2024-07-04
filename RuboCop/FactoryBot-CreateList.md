Pattern: Malformed use of `create_list`

Issue: -

## Description

Checks for `create_list` usage.

This rule can be configured using the `EnforcedStyle` option.

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

## Further Reading

* [FactoryBot/CreateList](https://docs.rubocop.org/rubocop-factory_bot/cops_factorybot.html#factorybotcreatelist)