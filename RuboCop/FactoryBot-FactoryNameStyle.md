Pattern: Inconsistent style for `FactoryBot::Syntax::Methods`

Issue: -

## Description

Checks for name style for argument of `FactoryBot::Syntax::Methods`.

## Examples

#### `EnforcedStyle: symbol (default)`

```ruby
# bad
create('user')
build "user", username: "NAME"

# good
create(:user)
build :user, username: "NAME"
```

#### `EnforcedStyle: string`

```ruby
# bad
create(:user)
build :user, username: "NAME"

# good
create('user')
build "user", username: "NAME"
```

## Further Reading

* [FactoryBot/FactoryNameStyle](https://docs.rubocop.org/rubocop-factory_bot/cops_factorybot.html#factorybotfactorynamestyle)
