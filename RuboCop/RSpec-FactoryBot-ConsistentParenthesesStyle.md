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

## Configurable attributes

Name | Default value | Configurable values
--- | --- | ---
EnforcedStyle | `require_parentheses` | `require_parentheses`, `omit_parentheses`

## Further Reading

* [RSpec - RSpec/FactoryBot/ConsistentParenthesesStyle](https://docs.rubocop.org/rubocop-rspec/cops_rspec_factorybot.html#rspecfactorybotconsistentparenthesesstyle)
* https://www.rubydoc.info/gems/rubocop-rspec/RuboCop/Cop/RSpec/FactoryBot/ConsistentParenthesesStyle