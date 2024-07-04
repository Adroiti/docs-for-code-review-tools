Pattern: Inconsistent parentheses for factory bot

Issue: -

## Description

Use a consistent style for parentheses in factory bot calls.

## Examples

```ruby
# bad
create :user
build(:user)
create(:login)
create :login
```

#### `EnforcedStyle: require_parentheses` (default)

```ruby
# good
create(:user)
create(:user)
create(:login)
build(:login)
```

#### `EnforcedStyle: omit_parentheses`

```ruby
# good
create :user
build :user
create :login
create :login

# also good
# when method name and first argument are not on same line
create(
  :user
)
build(
  :user,
  name: 'foo'
)
```

## Further Reading

* [FactoryBot/ConsistentParenthesesStyle](https://docs.rubocop.org/rubocop-factory_bot/cops_factorybot.html#factorybotconsistentparenthesesstyle)