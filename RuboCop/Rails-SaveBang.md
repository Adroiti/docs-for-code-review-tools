Pattern: Missing use of exception raising method

Issue: -

## Description

Identifies possible cases where Active Record save! or related
should be used instead of save because the model might have failed to
save and an exception is better than unhandled failure.

This will allow:

- update or save calls, assigned to a variable,
  or used as a condition in an if/unless/case statement.
- create calls, assigned to a variable that then has a
  call to `persisted?`, or whose return value is checked by
  `persisted?` immediately
- calls if the result is explicitly returned from methods and blocks,
  or provided as arguments.
- calls whose signature doesn't look like an ActiveRecord
  persistence method.

By default it will also allow implicit returns from methods and blocks.
that behavior can be turned off with `AllowImplicitReturn: false`.

You can permit receivers that are giving false positives with
`AllowedReceivers: []`

## Examples

```ruby
# bad
user.save
user.update(name: 'Joe')
user.find_or_create_by(name: 'Joe')
user.destroy

# good
unless user.save
   . . .
end
user.save!
user.update!(name: 'Joe')
user.find_or_create_by!(name: 'Joe')
user.destroy!

user = User.find_or_create_by(name: 'Joe')
unless user.persisted?
   . . .
end
```

## Further Reading

* [RuboCop - Rails/SaveBang](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railssavebang)
* [https://github.com/bbatsov/rails-style-guide#save-bang](https://github.com/bbatsov/rails-style-guide#save-bang)
