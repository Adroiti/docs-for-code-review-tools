Pattern: Use of _ActiveRecord_ alias

Issue: -

## Description

Checks that _ActiveRecord_ aliases are not used. The direct method names are more clear and easier to read.

## Examples

```ruby
#bad
Book.update_attributes!(author: 'Alice')

#good
Book.update!(author: 'Alice')
```

## Further Reading

* [RuboCop - Rails/ActiveRecordAliases](https://github.com/rubocop-hq/rubocop-rails/tree/master/lib/rubocop/cop/rails#railsactiverecordaliases)
