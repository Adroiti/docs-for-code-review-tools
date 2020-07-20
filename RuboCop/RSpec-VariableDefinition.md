Pattern: Malformed memoized helper definition

Issue: -

## Description

Checks that memoized helpers names are symbols or strings.

## Examples

```ruby
# bad
let('user_name') { 'Adam' }
subject('user') { create_user }

# good
let(:user_name) { 'Adam' }
subject(:user) { create_user }
```

## Further Reading

* [RSpec - RSpec/VariableDefinition](https://docs.rubocop.org/rubocop-rspec/cops_rspec.adoc#rspecvariabledefinition)