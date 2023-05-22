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

* [RSpec - RSpec/FactoryBot/FactoryNameStyle](https://docs.rubocop.org/rubocop-rspec/cops_rspec_factorybot.html#rspecfactorybotfactorynamestyle)
