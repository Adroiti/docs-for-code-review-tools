Pattern: Inconsistent use of `exists?`

Issue: -

## Description

This rule enforces consistent style when using `exists?`.

When EnforcedStyle is 'exists' then the rule enforces `exists?(…​)` over `where(…​).exists?`.
When EnforcedStyle is 'where' then the rule enforces `where(…​).exists?` over `exists?(…​)`.

## Examples

#### EnforcedStyle: exists (default)

```ruby
# bad
User.where(name: 'john').exists?
User.where(['name = ?', 'john']).exists?
User.where('name = ?', 'john').exists?
user.posts.where(published: true).exists?

# good
User.exists?(name: 'john')
User.where('length(name) > 10').exists?
user.posts.exists?(published: true)
```

#### EnforcedStyle: where

```ruby
# bad
User.exists?(name: 'john')
User.exists?(['name = ?', 'john'])
User.exists?('name = ?', 'john')
user.posts.exists?(published: true)

# good
User.where(name: 'john').exists?
User.where(['name = ?', 'john']).exists?
User.where('name = ?', 'john').exists?
user.posts.where(published: true).exists?
User.where('length(name) > 10').exists?
```

## Further Reading

* [RuboCop - Rails/WhereExists](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railswhereexists)
