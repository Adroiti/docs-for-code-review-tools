Pattern: Use of `pluck` before `uniq`/`distinct`

Issue: -

## Description

Prefer the use of `uniq` (or `distinct`) before `pluck` instead of after.

The use of `uniq` before `pluck` is preferred because it executes within
the database.

This rule has two different enforcement modes. When the _EnforcedStyle_
is conservative (the default) then only calls to `pluck` on a constant
(i.e. a model class) before `uniq` are added as offenses.

When the _EnforcedStyle_ is aggressive then all calls to `pluck` before
`uniq` are added as offenses. This may lead to false positives as the rule 
cannot distinguish between calls to `pluck` on an ActiveRecord::Relation
vs a call to `pluck` on an ActiveRecord::Associations::CollectionProxy.

## Examples

```ruby
# bad
Model.pluck(:id).uniq

# good
Model.uniq.pluck(:id)
```
```ruby
# this will return a Relation that pluck is called on
Model.where(...).pluck(:id).uniq

# an association on an instance will return a CollectionProxy
instance.assoc.pluck(:id).uniq
```

## Default configuration

Attribute | Value
--- | ---
EnforcedStyle | conservative
SupportedStyles | conservative, aggressive

## Further Reading

* [RuboCop - Rails/UniqBeforePluck](https://rubocop.readthedocs.io/en/latest/cops_rails/#railsuniqbeforepluck)
