Pattern: Use of `pluck` in `where`

Issue: -

## Description

This rule identifies places where `pluck` is used in `where` query methods and can be replaced with `select`.

Since `pluck` is an eager method and hits the database immediately, using `select` helps to avoid additional database queries.

This rule has two different enforcement modes. When the EnforcedStyle is conservative (the default) then only calls to `pluck` on a constant (i.e. a model class) in the where is used as offenses.

When the EnforcedStyle is aggressive then all calls to `pluck` in the where is used as offenses. This may lead to false positives as the rule cannot replace to `select` between calls to `pluck` on an `ActiveRecord::Relation` instance vs a call to `pluck` on an `Array` instance.

## Examples

```ruby
# bad
Post.where(user_id: User.active.pluck(:id))

# good
Post.where(user_id: User.active.select(:id))
Post.where(user_id: active_users.select(:id))
```

#### EnforcedStyle: conservative (default)

```ruby
# good
Post.where(user_id: active_users.pluck(:id))
```

#### EnforcedStyle: aggressive

```ruby
# bad
Post.where(user_id: active_users.pluck(:id))
```

## Further Reading

* [RuboCop - Rails/PluckInWhere](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railspluckinwhere)
