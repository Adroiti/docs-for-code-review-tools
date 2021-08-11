Pattern: Missing use of `Arel.star` instead of `"*"`

Issue: -

## Description

Prevents usage of `"*"` on an Arel::Table column reference.

Using `arel_table["*"]` causes the outputted string to be a literal
quoted asterisk (e.g. <tt>`my_model`.`*`</tt>). This causes the
database to look for a column named <tt>`*`</tt> (or `"*"`) as opposed
to expanding the column list as one would likely expect.

## Examples

```ruby
# bad
MyTable.arel_table["*"]

# good
MyTable.arel_table[Arel.star]
```

## Further Reading

* [RuboCop - Rails/ArelStar](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsarelstar)
