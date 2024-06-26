Pattern: Missing use of range in `where`

Issue: -

## Description

Identifies places where manually constructed SQL in where can be replaced with ranges.

## Examples

```ruby
# bad
User.where('age >= ?', 18)
User.where.not('age >= ?', 18)
User.where('age < ?', 18)
User.where('age >= ? AND age < ?', 18, 21)
User.where('age >= :start', start: 18)
User.where('users.age >= ?', 18)

# good
User.where(age: 18..)
User.where.not(age: 18..)
User.where(age: ...18)
User.where(age: 18...21)
User.where(users: { age: 18.. })

# good
# There are no beginless ranges in ruby.
User.where('age > ?', 18)
```

## Further Reading

* [RuboCop - Rails/WhereRange](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railswhererange)
